---
title: "_set_app_type | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _set_app_type
apilocation:
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _set_app_type
- corecrt_startup/_set_app_type
dev_langs:
- C++
ms.assetid: 1e7fe786-b587-4116-8c05-f7d762350100
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 86078a8ff66eadc1cdd6b177ba074abfd1683345
ms.lasthandoff: 02/24/2017

---
# <a name="setapptype"></a>_set_app_type
Внутренняя функция используется при запуске для того, чтобы сообщить CRT, является ли приложение консольным приложением или приложением с графическим интерфейсом.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum _crt_app_type
{
    _crt_unknown_app,
    _crt_console_app,
    _crt_gui_app
} _crt_app_type;

void __cdecl _set_app_type(
    _crt_app_type appType
    ); 
```  
  
## <a name="parameters"></a>Параметры  
 `appType`  
 Значение, указывающее на тип приложения. Допустимые значения:  
  
|Значение|Описание|  
|----------------|-----------------|  
|_crt_unknown_app|Неизвестный тип приложения.|  
|_crt_console_app|Приложение консоли (командной строки).|  
|_crt_gui_app|Приложение с графическим интерфейсом (Windows).|  
  
## <a name="remarks"></a>Примечания  
 Обычно вызывать эту функцию не нужно. Она входит в код запуска среды выполнения C, который выполняется перед вызовом `main` в приложении.
 
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|_set_app_type|process.h|


