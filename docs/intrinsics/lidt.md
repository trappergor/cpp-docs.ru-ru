---
title: __lidt
ms.date: 11/04/2016
f1_keywords:
- __lidt
- __lidt_cpp
helpviewer_keywords:
- LIDT instruction
- __lidt intrinsic
ms.assetid: 8298d25d-a19e-4900-828d-6b3b09841882
ms.openlocfilehash: 757309603af48820a17668cfe272bbeaad9239b3
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59038477"
---
# <a name="lidt"></a>__lidt

**Блок, относящийся только к системам Microsoft**

Загружает регистр таблицу дескриптора прерывания (IDTR) со значением в указанной области памяти.

## <a name="syntax"></a>Синтаксис

```
void __lidt(void * Source);
```

#### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*Исходный код*|[in] Указатель на значение для копирования IDTR.|

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__lidt`|x86, x64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

`__lidt` Функция эквивалентна `LIDT` инструкции компьютера и доступна только в режиме ядра. Дополнительные сведения см. в документе «Руководство разработчика архитектуры Intel программного обеспечения, том 2: Справочник по набору инструкций,» в [корпорации Intel](https://software.intel.com/articles/intel-sdm) сайта.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)<br/>
[__sidt](../intrinsics/sidt.md)