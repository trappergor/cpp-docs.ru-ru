---
title: __sidt | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __sidt
dev_langs:
- C++
helpviewer_keywords:
- sidt instruction
- __sidt intrinsic
ms.assetid: 01e83d14-6e63-4dea-8f64-5a0339d69641
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dbfb0b50e31cc51c7ea860fbd7b78c89a652ac64
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46429376"
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

`__sidt` Функция эквивалентна `SIDT` инструкции компьютера. Дополнительные сведения см. в документе «Руководство разработчика архитектуры Intel программного обеспечения, том 2: ссылка на набор инструкций,» в [корпорации Intel](https://software.intel.com/en-us/articles/intel-sdm) сайта.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)<br/>
[__lidt](../intrinsics/lidt.md)