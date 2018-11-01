---
title: __sidt
ms.date: 11/04/2016
f1_keywords:
- __sidt
helpviewer_keywords:
- sidt instruction
- __sidt intrinsic
ms.assetid: 01e83d14-6e63-4dea-8f64-5a0339d69641
ms.openlocfilehash: 2188b2cdbf5c5f8836197f8cf2ee33928b7e9425
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50624462"
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

Функция `__sidt` эквивалентна инструкции компьютера `SIDT` . Дополнительные сведения см. в документе «Руководство разработчика архитектуры Intel программного обеспечения, том 2: ссылка на набор инструкций,» в [корпорации Intel](https://software.intel.com/articles/intel-sdm) сайта.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)<br/>
[__lidt](../intrinsics/lidt.md)