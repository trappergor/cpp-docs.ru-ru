---
title: Класс enable_shared_from_this | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- memory/std::enable_shared_from_this
dev_langs:
- C++
helpviewer_keywords:
- enable_shared_from_this class
- enable_shared_from_this
ms.assetid: 9237603d-22e2-421f-b070-838ac006baf5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d74db7e9c88baec8aad7f966c0af3f2ec7840f0a
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44110556"
---
# <a name="enablesharedfromthis-class"></a>Класс enable_shared_from_this

Помогает сформировать `shared_ptr`.

## <a name="syntax"></a>Синтаксис

```cpp
class enable_shared_from_this {
public:
    shared_ptr<Ty>
        shared_from_this();
    shared_ptr<const Ty> shared_from_this() const;
protected:
    enable_shared_from_this();
    enable_shared_from_this(const enable_shared_from_this&);
    enable_shared_from_this& operator=(const enable_shared_from_this&);
    ~enable_shared_from_this();
};
```

### <a name="parameters"></a>Параметры

*Ty*<br/>
Тип, управляемый общим указателем.

## <a name="remarks"></a>Примечания

Объекты, производные от `enable_shared_from_this`, могут использовать методы `shared_from_this` в функциях-членах для создания владельцев [shared_ptr](../standard-library/shared-ptr-class.md) экземпляра, которые владеют им совместно с существующими владельцами `shared_ptr`. В противном случае, если вы создаете новый `shared_ptr` с помощью **это**, отличается от существующих `shared_ptr` владельцев, что может привести к недействительным ссылкам или вызовет объект будет удален несколько раз.

Во избежание случайного неправильного использования конструктор, деструктор и оператор присваивания защищены. Тип аргумента шаблона *Ty* должен быть типом производного класса.

Пример использования см. в разделе [enable_shared_from_this::shared_from_this](#shared_from_this).

## <a name="requirements"></a>Требования

**Заголовок:** \<memory>

**Пространство имен:** std

## <a name="shared_from_this"></a>  enable_shared_from_this::shared_from_this

Создает `shared_ptr`, который владеет экземпляром совместно с существующими владельцами `shared_ptr`.

```cpp
shared_ptr<T> shared_from_this();
shared_ptr<const T> shared_from_this() const;
```

### <a name="remarks"></a>Примечания

При получении объектов из базового класса `enable_shared_from_this` функции члена шаблона `shared_from_this` возвращают объект [класса shared_ptr](../standard-library/shared-ptr-class.md), владеющий данным экземпляром совместно с существующими владельцами `shared_ptr`. В противном случае, если вы создаете новый `shared_ptr` из **это**, отличается от существующих `shared_ptr` владельцев, что может привести к недействительным ссылкам или вызовет объект будет удален несколько раз. Поведение будет неопределенным, если вызвать `shared_from_this` в экземпляре, которым еще не владеет объект `shared_ptr`.

### <a name="example"></a>Пример

```cpp
// std_memory_shared_from_this.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

using namespace std;

struct base : public std::enable_shared_from_this<base>
{
    int val;
    shared_ptr<base> share_more()
    {
        return shared_from_this();
    }
};

int main()
{
    auto sp1 = make_shared<base>();
    auto sp2 = sp1->share_more();

    sp1->val = 3;
    cout << "sp2->val == " << sp2->val << endl;
    return 0;
}
```

```Output
sp2->val == 3
```

## <a name="see-also"></a>См. также

[enable_shared_from_this::shared_from_this](#shared_from_this)<br/>
[Класс shared_ptr](../standard-library/shared-ptr-class.md)<br/>