---
title: public (C++)
ms.date: 11/04/2016
f1_keywords:
- public_cpp
helpviewer_keywords:
- public keyword [C++]
ms.assetid: f3e10a59-39f6-4bcd-827e-3e99f8f89497
ms.openlocfilehash: dd45430543ead7258096be8f3d8cef0141f27b4e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179196"
---
# <a name="public-c"></a>public (C++)

## <a name="syntax"></a>Синтаксис

```
public:
   [member-list]
public base-class
```

## <a name="remarks"></a>Remarks

Когда список членов класса предшествует, ключевое слово **Public** указывает, что эти элементы доступны из любой функции. Это применяется ко всем членам, объявленным до следующего описателя доступа или до конца класса.

Когда имя базового класса предшествует, ключевое слово **Public** указывает, что открытые и защищенные члены базового класса являются открытыми и защищенными членами, соответственно производным классом.

Доступ членов в классе по умолчанию является закрытым. Доступ членов в структуре или объединении по умолчанию является открытым.

Доступ базового класса по умолчанию является закрытым для классов и открытым для структур. Объединения не могут иметь базовые классы.

Дополнительные сведения см. в статьях [закрытые](../cpp/private-cpp.md), [защищенные](../cpp/protected-cpp.md), [дружественные](../cpp/friend-cpp.md)и таблица доступа к членам в разделе [Управление доступом к членам класса](member-access-control-cpp.md).

## <a name="clr-specific"></a>Специально для /clr

В типах CLR ключевые слова C++ спецификатора доступа (**открытый**, **частный**и **защищенный**) могут влиять на видимость типов и методов в отношении сборок. Дополнительные сведения см. в разделе [Управление доступом к членам](member-access-control-cpp.md).

> [!NOTE]
>  Это поведение не влияет на файлы, скомпилированные с параметром [/LN](../build/reference/ln-create-msil-module.md) . В этом случае все управляемые классы (открытые или закрытые) будут видны.

## <a name="end-clr-specific"></a>КОНЕЦ специально для /clr

## <a name="example"></a>Пример

```cpp
// keyword_public.cpp
class BaseClass {
public:
   int pubFunc() { return 0; }
};

class DerivedClass : public BaseClass {};

int main() {
   BaseClass aBase;
   DerivedClass aDerived;
   aBase.pubFunc();       // pubFunc() is accessible
                          //    from any function
   aDerived.pubFunc();    // pubFunc() is still public in
                          //    derived class
}
```

## <a name="see-also"></a>См. также раздел

[Управление доступом к членам классов](member-access-control-cpp.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)
