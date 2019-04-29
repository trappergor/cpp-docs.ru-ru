---
title: Изменяемые члены данных (C++)
ms.date: 11/04/2016
f1_keywords:
- mutable_cpp
helpviewer_keywords:
- mutable keyword [C++]
ms.assetid: ebe89746-3d36-43a8-8d69-f426af23f551
ms.openlocfilehash: 8d592eb97f70bfc26c075317c57ec4d5c78e3956
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62301595"
---
# <a name="mutable-data-members-c"></a>Изменяемые члены данных (C++)

Это ключевое слово может применяться только к данным-членам класса, которые не являются статическими или константами. Если данные-член объявлены **изменяемый**, а затем можно присвоить значение этого элемента данных из **const** функция-член.

## <a name="syntax"></a>Синтаксис

```
mutable member-variable-declaration;
```

## <a name="remarks"></a>Примечания

Например, следующий код компилируется без ошибок, так как `m_accessCount` был объявлен **изменяемый**и поэтому могут быть изменены `GetFlag` несмотря на то что `GetFlag` является постоянная функция-член.

```cpp
// mutable.cpp
class X
{
public:
   bool GetFlag() const
   {
      m_accessCount++;
      return m_flag;
   }
private:
   bool m_flag;
   mutable int m_accessCount;
};

int main()
{
}
```

## <a name="see-also"></a>См. также

[Ключевые слова](../cpp/keywords-cpp.md)