---
title: __sidt
ms.date: 11/04/2016
f1_keywords:
- __sidt
helpviewer_keywords:
- sidt instruction
- __sidt intrinsic
ms.assetid: 01e83d14-6e63-4dea-8f64-5a0339d69641
ms.openlocfilehash: 88dbb4713577fcf224e1c5646bf4c38b2a1dfafe
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59036764"
---
# <a name="sidt"></a>__sidt

**Блок, относящийся только к системам Microsoft**

Сохраняет значение регистра таблицу дескриптора прерываний (IDTR) в указанной области памяти.

## <a name="syntax"></a>Синтаксис

```
void __sidt(void * Destination);
```

#### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*Назначение*|[in] Указатель на область памяти, где хранится IDTR.|

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__sidt`|x86, x64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

Функция `__sidt` эквивалентна инструкции компьютера `SIDT` . Дополнительные сведения см. в документе «Руководство разработчика архитектуры Intel программного обеспечения, том 2: Справочник по набору инструкций,» в [корпорации Intel](https://software.intel.com/articles/intel-sdm) сайта.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)<br/>
[__lidt](../intrinsics/lidt.md)