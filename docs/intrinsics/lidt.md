---
title: __lidt
ms.date: 09/02/2019
f1_keywords:
- __lidt
- __lidt_cpp
helpviewer_keywords:
- LIDT instruction
- __lidt intrinsic
ms.assetid: 8298d25d-a19e-4900-828d-6b3b09841882
ms.openlocfilehash: 24778b761ada56830b155a2fc65e90f54ba729ed
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217505"
---
# <a name="__lidt"></a>__lidt

**Блок, относящийся только к системам Microsoft**

Загружает регистр таблицы дескрипторов прерываний (ИДТР) со значением в указанном расположении в памяти.

## <a name="syntax"></a>Синтаксис

```C
void __lidt(void * Source);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*Source*|окне Указатель на значение, которое должно быть скопировано в ИДТР.|

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__lidt`|x86, x64|

**Заголовочный файл** \<> Intrin. h

## <a name="remarks"></a>Примечания

Функция эквивалентна инструкции компьютера и доступна только в режиме ядра. `LIDT` `__lidt` Дополнительные сведения см. в документе "Руководство разработчика по архитектуры Intel, том 2: Справочник по набору инструкций "на сайте корпорации [Intel](https://software.intel.com/articles/intel-sdm) .

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)\
[__sidt](../intrinsics/sidt.md)
