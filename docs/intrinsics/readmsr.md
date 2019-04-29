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
ms.openlocfilehash: 2c866213c452f3b8791bf0fe031a43bb024e91fb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62262779"
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