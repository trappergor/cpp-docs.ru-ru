---
title: Класс bad_weak_ptr | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- memory/std::bad_weak_ptr
dev_langs:
- C++
helpviewer_keywords:
- bad_weak_ptr
- bad_weak_ptr class
ms.assetid: a09336d5-7237-4480-ab6b-3787e0e6025e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8cb6e00341e5e40d04be1d447f03e43818e53291
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33839836"
---
# <a name="badweakptr-class"></a>Класс bad_weak_ptr

Сообщает о необрабатываемом исключении weak_ptr.

## <a name="syntax"></a>Синтаксис

```cpp
class bad_weak_ptr : public std::exception
 {
public:
    bad_weak_ptr();
    const char *what() throw();
 };
```

## <a name="remarks"></a>Примечания

Данный класс описывает исключение, которое может быть создано из конструктора [класса shared_ptr](../standard-library/shared-ptr-class.md), принимающего аргумент типа [weak_ptr](../standard-library/weak-ptr-class.md). Функция-член `what` возвращает значение `"bad_weak_ptr"`.

## <a name="example"></a>Пример

```cpp
// std__memory__bad_weak_ptr.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::weak_ptr<int> wp;

    {
        std::shared_ptr<int> sp(new int);
        wp = sp;
    }

    try
    {
        std::shared_ptr<int> sp1(wp); // weak_ptr has expired
    }
    catch (const std::bad_weak_ptr&)
    {
        std::cout << "bad weak pointer" << std::endl;
    }
    catch (...)
    {
        std::cout << "unknown exception" << std::endl;
    }

    return (0);
}
```

```Output
bad weak pointer
```

## <a name="requirements"></a>Требования

**Заголовок:** \<memory>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Класс weak_ptr](../standard-library/weak-ptr-class.md)<br/>
