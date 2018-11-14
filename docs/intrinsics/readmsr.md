---
title: __readmsr
ms.date: 11/04/2016
f1_keywords:
- __readmsr
helpviewer_keywords:
- Read Model Specific Register
- rdmsr instruction
- __readmsr intrinsic
ms.assetid: 7ab1f8e8-72cb-4ce4-817d-3e728a3c9716
ms.openlocfilehash: 891ca43af4a81b63de39d367ea418e43811f78d0
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2018
ms.locfileid: "51326411"
---
# <a name="readmsr"></a>__readmsr

**Блок, относящийся только к системам Microsoft**

Создает `rdmsr` инструкция, которая считывает регистр конкретной модели, определяемое `register` и возвращает его значение.

## <a name="syntax"></a>Синтаксис

```
__int64 __readmsr(
   int register
);
```

#### <a name="parameters"></a>Параметры

*register*<br/>
[in] Модельнозависимого регистра для чтения.

## <a name="return-value"></a>Возвращаемое значение

Значение в указанном регистре.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__readmsr`|x86, x64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

Эта функция доступна только в режиме ядра и процедура доступна только как встроенная.

Дополнительные сведения см. в документации AMD.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)