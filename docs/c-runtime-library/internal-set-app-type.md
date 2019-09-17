---
title: __set_app_type
ms.date: 11/04/2016
api_name:
- __set_app_type
- _set_app_type
api_location:
- msvcr90.dll
- msvcr100.dll
- msvcr110.dll
- msvcr80.dll
- msvcrt.dll
- msvcr120.dll
- msvcr110_clr0400.dll
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __set_app_type
helpviewer_keywords:
- __set_app_type
ms.assetid: f0ac0f4d-70e6-4e96-9e43-eb9d1515490c
ms.openlocfilehash: 4d72eecd454e6c01e88c6869c96b628902690383
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70940228"
---
# <a name="__set_app_type"></a>__set_app_type

Задает тип текущего приложения.

## <a name="syntax"></a>Синтаксис

```cpp
void __set_app_type (
   int at
   )
```

#### <a name="parameters"></a>Параметры

*at*<br/>
Значение, указывающее на тип приложения. Допустимые значения:

|Значение|ОПИСАНИЕ|
|-----------|-----------------|
|_UNKNOWN_APP|Неизвестный тип приложения.|
|_CONSOLE_APP|Приложение консоли (командной строки).|
|_GUI_APP|Приложение с графическим интерфейсом (Windows).|

## <a name="remarks"></a>Примечания

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|__set_app_type|internal.h|