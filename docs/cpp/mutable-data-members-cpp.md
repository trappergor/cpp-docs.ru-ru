---
title: Изменяемые данные-члены (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- mutable_cpp
dev_langs:
- C++
helpviewer_keywords:
- mutable keyword [C++]
ms.assetid: ebe89746-3d36-43a8-8d69-f426af23f551
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: de0a208341e6a687d1319c4d8d60cc8671555dd6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46107006"
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