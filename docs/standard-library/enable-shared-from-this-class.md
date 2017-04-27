---
title: "Класс enable_shared_from_this | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- enable_shared_from_this
- memory/std::enable_shared_from_this
dev_langs:
- C++
helpviewer_keywords:
- enable_shared_from_this class
- enable_shared_from_this
ms.assetid: 9237603d-22e2-421f-b070-838ac006baf5
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: f293f074f2b8e2334dc70fbebba8e6f4c17efecc
ms.openlocfilehash: 7f32ee8a40da16ac919f0c3d8be05573f7b78c3a
ms.lasthandoff: 02/24/2017

---
# <a name="enablesharedfromthis-class"></a>Класс enable_shared_from_this
Помогает сформировать `shared_ptr`.  
  
## <a name="syntax"></a>Синтаксис  
```    
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
#### <a name="parameters"></a>Параметры  
 `Ty`  
 Тип, управляемый общим указателем.  
  
## <a name="remarks"></a>Примечания  
 Объекты, производные от `enable_shared_from_this`, могут использовать методы `shared_from_this` в функциях-членах для создания владельцев [shared_ptr](../standard-library/shared-ptr-class.md) экземпляра, которые владеют им совместно с существующими владельцами `shared_ptr`. В противном случае, если создается новый `shared_ptr` с помощью `this`, он отличается от существующих владельцев `shared_ptr`, что может привести к недействительным ссылкам или к тому, что объект будет удален несколько раз.  
  
 Во избежание случайного неправильного использования конструктор, деструктор и оператор присваивания защищены. Тип аргумента шаблона `Ty` должен быть типом производного класса.  
  
 Пример использования см. в разделе [enable_shared_from_this::shared_from_this](#enable_shared_from_this__shared_from_this).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<memory>  
  
 **Пространство имен:** std  
  
##  <a name="enable_shared_from_this__shared_from_this"></a>  enable_shared_from_this::shared_from_this  
 Создает `shared_ptr`, который владеет экземпляром совместно с существующими владельцами `shared_ptr`.  
  
```  
shared_ptr<T> shared_from_this();
shared_ptr<const T> shared_from_this() const;
```  
  
### <a name="remarks"></a>Примечания  
 При получении объектов из базового класса `enable_shared_from_this` функции члена шаблона `shared_from_this` возвращают объект [класса shared_ptr](../standard-library/shared-ptr-class.md), владеющий данным экземпляром совместно с существующими владельцами `shared_ptr`. В противном случае, если создается новый `shared_ptr` из `this`, он отличается от существующих владельцев `shared_ptr`, что может привести к недействительным ссылкам или к тому, что объект будет удален несколько раз. Поведение будет неопределенным, если вызвать `shared_from_this` в экземпляре, которым еще не владеет объект `shared_ptr`.  
  
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
 [enable_shared_from_this::shared_from_this](#enable_shared_from_this__shared_from_this)   
 [Класс shared_ptr](../standard-library/shared-ptr-class.md)
