---
title: _ReadBarrier | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _ReadBarrier
dev_langs:
- C++
helpviewer_keywords:
- _ReadBarrier intrinsic
ms.assetid: f9e54a92-61bc-4f55-8195-b8932065a796
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b121a849f3f1678becb2175bd284d036b534e8e2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46441386"
---
# <a name="readbarrier"></a>_ReadBarrier

**Блок, относящийся только к системам Microsoft**

Ограничивает оптимизации компилятора, которые могут изменить порядок операций доступа к памяти для точки вызова.

> [!CAUTION]
>  Встроенные функции компилятора `_ReadBarrier`, `_WriteBarrier` и `_ReadWriteBarrier`, а также макрос `MemoryBarrier` являются нерекомендуемыми, и использовать их не следует. Для взаимодействия между потоками, используют механизмы, например [atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence) и [std::atomic\<T >](../standard-library/atomic.md) , определенные в [стандартной библиотеки C++](../standard-library/cpp-standard-library-reference.md). Для доступа к оборудованию, используйте [/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md) параметр компилятора вместе с [volatile](../cpp/volatile-cpp.md) ключевое слово.

## <a name="syntax"></a>Синтаксис

```
void _ReadBarrier(void);
```

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`_ReadBarrier`|x86, x64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

Встроенная функция `_ReadBarrier` ограничивает оптимизации компилятора, которые могут удалять или изменять порядок операций доступа к памяти для точки вызова.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)