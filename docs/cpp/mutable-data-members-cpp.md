---
title: Изменяемые данные-члены (C++)
ms.date: 11/04/2016
f1_keywords:
- mutable_cpp
helpviewer_keywords:
- mutable keyword [C++]
ms.assetid: ebe89746-3d36-43a8-8d69-f426af23f551
ms.openlocfilehash: db3a9594a77a9ada971213eaea74a9842bd96a54
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179345"
---
# <a name="mutable-data-members-c"></a>Изменяемые данные-члены (C++)

Это ключевое слово может применяться только к данным-членам класса, которые не являются статическими или константами. Если элемент данных объявлен как **изменяемый**, ему допустимо присвоить значение этому элементу данных из функции-члена **const** .

## <a name="syntax"></a>Синтаксис

```
mutable member-variable-declaration;
```

## <a name="remarks"></a>Remarks

Например, следующий код будет компилироваться без ошибок, так как `m_accessCount` объявлена как **изменяемая**, и поэтому может быть изменена `GetFlag` даже несмотря на то, что `GetFlag` является константной функцией-членом.

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

## <a name="see-also"></a>См. также раздел

[Ключевые слова](../cpp/keywords-cpp.md)
