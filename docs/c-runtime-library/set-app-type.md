---
title: _set_app_type
ms.date: 11/04/2016
api_name:
- _set_app_type
api_location:
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _set_app_type
- corecrt_startup/_set_app_type
ms.assetid: 1e7fe786-b587-4116-8c05-f7d762350100
ms.openlocfilehash: 7e04d88d9e9981e35b7d4c80c11d27c868219f65
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957926"
---
# <a name="_set_app_type"></a>_set_app_type

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

*appType*<br/>
Значение, указывающее на тип приложения. Допустимые значения:

|Значение|ОПИСАНИЕ|
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
