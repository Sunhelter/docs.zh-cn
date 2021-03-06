---
title: CorDebugPlatform 枚举
ms.date: 03/30/2017
api_name:
- CorDebugPlatformEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugPlatformEnum
helpviewer_keywords:
- CorDebugPlatformEnum enumeration [.NET Framework debugging]
ms.assetid: c5444816-7378-4521-afd3-bf5e4b5303d5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03b6f1b29157889d0e84e5dddc94d5e3ae27efce
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59180930"
---
# <a name="cordebugplatform-enumeration"></a>CorDebugPlatform 枚举
提供了使用的目标平台值[icordebugdatatarget:: Getplatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md)方法。  
  
## <a name="syntax"></a>语法  
  
```  
typedef enum CorDebugPlatform  
{  
    CORDB_PLATFORM_WINDOWS_X86,    // Windows on Intel x86  
    CORDB_PLATFORM_WINDOWS_AMD64,  // Windows x64 (AMD64, Intel EM64T)  
    CORDB_PLATFORM_WINDOWS_IA64,   // Windows on Intel IA-64  
    CORDB_PLATFORM_MAC_PPC,        // Macintosh OS on PowerPC  
    CORDB_PLATFORM_MAC_X86,        // Macintosh OS on Intel x86  
    CORDB_PLATFORM_WINDOWS_ARM,    // Windows on ARM  
    CORDB_PLATFORM_MAC_AMD64       // MacOS on Intel x64  
} CorDebugPlatform;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|CORDB_PLATFORM_WINDOWS_X86|目标平台是在 Intel x86 硬件上运行的 Windows。|  
|CORDB_PLATFORM_WINDOWS_AMD64|目标平台是在 AMD64 或 Intel EM64T 硬件上运行的 64 位 Windows。|  
|CORDB_PLATFORM_WINDOWS_IA64|目标平台是在 Intel IA-64 硬件上运行的 32 位 Windows。|  
|CORDB_PLATFORM_MAC_PPC|目标平台是在 PowerPC 硬件上运行的 Macintosh 操作系统。|  
|CORDB_PLATFORM_MAC_X86|目标平台是在 Intel x86 硬件上运行的 Macintosh 操作系统。|  
|CORDB_PLATFORM_WINDOWS_ARM|目标平台是在 Windows ARM 硬件上运行的 Macintosh 操作系统。|  
|CORDB_PLATFORM_MAC_AMD64|目标平台是在 AMD64 硬件上运行的 Macintosh 操作系统。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
 `CORDB_PLATFORM_WINDOWS_ARM` 成员和 `CORDB_PLATFORM_MAC_AMD64` 成员在 .NET Framework 4.5.2 及更高版本中可用。  
  
## <a name="see-also"></a>请参阅

- [调试枚举](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
