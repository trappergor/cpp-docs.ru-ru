---
title: Класс bad_array_new_length
ms.date: 11/04/2016
f1_keywords:
- new/std::bad_alloc
helpviewer_keywords:
- bad_alloc class
ms.assetid: 6429a8e6-5a49-4907-8d56-f4a4ec8131d0
ms.openlocfilehash: b00042513364ac04b62ac7e1943d912dcb78f212
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459487"
---
# <a name="badarraynewlength-class"></a>Класс bad_array_new_length

Класс описывает исключение, которое указывает, что запрос на выделение не был успешно выполнен из-за того, что размер массива меньше нуля или больше его ограничения.

## <a name="syntax"></a>Синтаксис

```cpp
class bad_array_new_length : public bad_alloc {
    public: bad_array_new_length() noexcept;
    const char* what() const noexcept override;
};
```

## <a name="remarks"></a>Примечания

Значение, возвращаемое `what` , является строкой C, определяемой реализацией. Ни одна из функций-членов не создает исключение.

## <a name="requirements"></a>Требования

**Заголовок:** \<new>

## <a name="see-also"></a>См. также

[Класс Exception](../standard-library/exception-class.md)\
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
