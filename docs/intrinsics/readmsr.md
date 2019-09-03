---
title: __readmsr
ms.date: 09/02/2019
f1_keywords:
- __readmsr
helpviewer_keywords:
- Read Model Specific Register
- rdmsr instruction
- __readmsr intrinsic
ms.assetid: 7ab1f8e8-72cb-4ce4-817d-3e728a3c9716
ms.openlocfilehash: 4398b9d42369e3a914dbec1ed2d14cafecf58483
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222335"
---
# <a name="__readmsr"></a>__readmsr

**Блок, относящийся только к системам Microsoft**

Формирует инструкцию, которая считывает регистр `register` , зависящий от модели, и возвращает его значение. `rdmsr`

## <a name="syntax"></a>Синтаксис

```C
__int64 __readmsr(
   int register
);
```

### <a name="parameters"></a>Параметры

*зарегистрировать*\
окне Зависящий от модели регистр для чтения.

## <a name="return-value"></a>Возвращаемое значение

Значение в указанном регистре.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__readmsr`|x86, x64|

**Заголовочный файл** \<> Intrin. h

## <a name="remarks"></a>Примечания

Эта функция доступна только в режиме ядра, и подпрограммы доступны только в качестве встроенных.

Дополнительные сведения см. в документации по AMD.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)
