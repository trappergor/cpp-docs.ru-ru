---
title: Структура nothrow_t
ms.date: 11/04/2016
f1_keywords:
- nothrow_t
helpviewer_keywords:
- nothrow_t class
ms.assetid: dc7d5d42-ed5a-4919-88fe-bbad519b7a1d
ms.openlocfilehash: bd65b5006326850522a251cbcf7d655133a1aa8a
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245582"
---
# <a name="nothrowt-structure"></a>Структура nothrow_t

Этот класс используется как параметр функции для оператора new, чтобы показать, что для сообщения об ошибке выделения памяти данная функция должна возвращать пустой указатель (NULL), а не вызывать исключение.

## <a name="syntax"></a>Синтаксис

```cpp
struct std::nothrow_t {};
```

## <a name="remarks"></a>Примечания

Структура помогает компилятору выбрать подходящую версию конструктора. [nothrow](../standard-library/new-functions.md#nothrow) является синонимом для объектов типа `std::nothrow_t`.

## <a name="example"></a>Пример

См. разделы [operator new](../standard-library/new-operators.md#op_new) и [operator new&#91;&#93;](../standard-library/new-operators.md#op_new_arr) с примерами использования `std::nothrow_t` в качестве параметра функции.
