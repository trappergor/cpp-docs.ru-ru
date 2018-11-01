---
title: _WriteBarrier
ms.date: 11/04/2016
f1_keywords:
- _WriteBarrier
helpviewer_keywords:
- WriteBarrier intrinsic
- _WriteBarrier intrinsic
ms.assetid: a5ffdad9-0ca1-4eb7-b2f3-0f092c4bf4b5
ms.openlocfilehash: b1b5ba2d70a8fc64eb47b3c6f3ff157214dcb94d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50653028"
---
# <a name="writebarrier"></a>_WriteBarrier

**Блок, относящийся только к системам Microsoft**

Ограничивает оптимизации компилятора, которые могут изменить порядок операций доступа к памяти для точки вызова.

> [!CAUTION]
>  Встроенные функции компилятора `_ReadBarrier`, `_WriteBarrier` и `_ReadWriteBarrier`, а также макрос `MemoryBarrier` являются нерекомендуемыми, и использовать их не следует. Для взаимодействия между потоками, используют механизмы, например [atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence) и [std::atomic\<T >](../standard-library/atomic.md), которые определены в [стандартной библиотеки C++](../standard-library/cpp-standard-library-reference.md). Для доступа к оборудованию, используйте [/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md) параметр компилятора вместе с [volatile](../cpp/volatile-cpp.md) ключевое слово.

## <a name="syntax"></a>Синтаксис

```
void _WriteBarrier(void);
```

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`_WriteBarrier`|x86, x64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

Встроенная функция `_WriteBarrier` ограничивает оптимизации компилятора, которые могут удалять или изменять порядок операций доступа к памяти для точки вызова.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[_ReadBarrier](../intrinsics/readbarrier.md)<br/>
[_ReadWriteBarrier](../intrinsics/readwritebarrier.md)<br/>
[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)