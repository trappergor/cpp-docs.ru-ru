---
title: _set_app_type
ms.date: 11/04/2016
apiname:
- _set_app_type
apilocation:
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _set_app_type
- corecrt_startup/_set_app_type
ms.assetid: 1e7fe786-b587-4116-8c05-f7d762350100
ms.openlocfilehash: f12e409355fcd10ece474103109286925b1f3a8d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50569823"
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

*appType*<br/>
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

