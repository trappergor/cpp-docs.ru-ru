---
title: _set_app_type | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fc9b3901cb031a1cc08d911889dc97818cfb5a44
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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
  
|Значение|Описание:|  
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

