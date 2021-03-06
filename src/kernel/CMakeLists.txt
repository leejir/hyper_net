INCLUDE_DIRECTORIES(
    "${PROJECT_SOURCE_DIR}/src/API/"
    "${PROJECT_SOURCE_DIR}/src/public/"
    "${PROJECT_SOURCE_DIR}/src/public/tinyxml"
    "${PROJECT_SOURCE_DIR}/src/kernel/"
    "${PROJECT_SOURCE_DIR}/src/kernel/config/"
    "${PROJECT_SOURCE_DIR}/src/kernel/net/"
    "${PROJECT_SOURCE_DIR}/src/kernel/lua/"
    "${PROJECT_SOURCE_DIR}/src/kernel/define/"
    "${PROJECT_SOURCE_DIR}/src/kernel/logic/"
	"${PROJECT_SOURCE_DIR}/src/kernel/logger/"
	"${PROJECT_SOURCE_DIR}/src/kernel/timer/"
	"${PROJECT_SOURCE_DIR}/src/kernel/async/"
    )

SET(KERNEL_CONFIG
    "${PROJECT_SOURCE_DIR}/src/kernel/config/ConfigMgr.h"
    "${PROJECT_SOURCE_DIR}/src/kernel/config/ConfigMgr.cpp"
    )
	
SET(KERNEL_ASYNC
    "${PROJECT_SOURCE_DIR}/src/kernel/async/AsyncMgr.h"
    "${PROJECT_SOURCE_DIR}/src/kernel/async/AsyncMgr.cpp"
	"${PROJECT_SOURCE_DIR}/src/kernel/async/AsyncBase.h"
    "${PROJECT_SOURCE_DIR}/src/kernel/async/AsyncBase.cpp"
	"${PROJECT_SOURCE_DIR}/src/kernel/async/AsyncThread.h"
    "${PROJECT_SOURCE_DIR}/src/kernel/async/AsyncThread.cpp"
    )

SET(KERNEL_NET
    "${PROJECT_SOURCE_DIR}/src/kernel/net/NetEngine.h"
    "${PROJECT_SOURCE_DIR}/src/kernel/net/NetEngine.cpp"
    "${PROJECT_SOURCE_DIR}/src/kernel/net/Connection.h"
    "${PROJECT_SOURCE_DIR}/src/kernel/net/Connection.cpp"
	"${PROJECT_SOURCE_DIR}/src/kernel/net/NetLoop.h"
    "${PROJECT_SOURCE_DIR}/src/kernel/net/NetLoop.c"
    )
	
SET(KERNEL_TIMER
    "${PROJECT_SOURCE_DIR}/src/kernel/timer/TimerMgr.h"
    "${PROJECT_SOURCE_DIR}/src/kernel/timer/TimerMgr.cpp"
	"${PROJECT_SOURCE_DIR}/src/kernel/timer/TimerGear.h"
    "${PROJECT_SOURCE_DIR}/src/kernel/timer/TimerGear.cpp"
	"${PROJECT_SOURCE_DIR}/src/kernel/timer/TimerList.h"
    "${PROJECT_SOURCE_DIR}/src/kernel/timer/TimerList.cpp"
	"${PROJECT_SOURCE_DIR}/src/kernel/timer/TimerBase.h"
    "${PROJECT_SOURCE_DIR}/src/kernel/timer/TimerBase.cpp"
    )

SET(KERNEL_LOGGER
    "${PROJECT_SOURCE_DIR}/src/kernel/logger/Logger.h"
    "${PROJECT_SOURCE_DIR}/src/kernel/logger/Logger.cpp"
    )

SET(KERNEL_LOGIC
    "${PROJECT_SOURCE_DIR}/src/kernel/logic/LogicMgr.h"
    "${PROJECT_SOURCE_DIR}/src/kernel/logic/LogicMgr.cpp"
    )

SET(KERNEL
    "${PROJECT_SOURCE_DIR}/src/kernel/kernel.h"
    "${PROJECT_SOURCE_DIR}/src/kernel/kernel.cpp"
    "${PROJECT_SOURCE_DIR}/src/kernel/main.cpp"
)

SOURCE_GROUP(src\\config FILES ${KERNEL_CONFIG})
SOURCE_GROUP(src\\net FILES ${KERNEL_NET})
SOURCE_GROUP(src\\logger FILES ${KERNEL_LOGGER})
SOURCE_GROUP(src\\logic FILES ${KERNEL_LOGIC})
SOURCE_GROUP(src\\timer FILES ${KERNEL_TIMER})
SOURCE_GROUP(src\\async FILES ${KERNEL_ASYNC})
SOURCE_GROUP(API FILES ${API})
SOURCE_GROUP(public\\tinyxml FILES ${PUBLIC_XML})
SOURCE_GROUP(public FILES ${PUBLIC})
SOURCE_GROUP(src FILES ${KERNEL})

ADD_EXECUTABLE(serverd
        ${API}
        ${KERNEL_CONFIG}
        ${KERNEL_NET}
		${KERNEL_TIMER}
        ${KERNEL_LOGIC}
        ${KERNEL_LOGGER}
		${KERNEL_ASYNC}
        ${PUBLIC}
        ${PUBLIC_XML}
        ${KERNEL}
        )

SET(EXECUTABLE_OUTPUT_PATH "${PROJECT_SOURCE_DIR}/bin")
