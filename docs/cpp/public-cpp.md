---
title: public (C++)
ms.date: 11/04/2016
f1_keywords:
- public_cpp
helpviewer_keywords:
- public keyword [C++]
ms.assetid: f3e10a59-39f6-4bcd-827e-3e99f8f89497
ms.openlocfilehash: bf8293c6a6cf12154b02979de08035807991052c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376048"
---
# <a name="public-c"></a>public (C++)

## <a name="syntax"></a>Синтаксис

```
public:
   [member-list]
public base-class
```

## <a name="remarks"></a>Remarks

При предшествующем списке членов класса, **в общедоступном** ключевом слове указывается, что эти участники доступны из любой функции. Это применяется ко всем членам, объявленным до следующего описателя доступа или до конца класса.

При предшествующем названию базового класса, **в общедоступном** ключевом слове указывается, что публичные и защищенные члены базового класса являются публичными и защищенными членами, соответственно, производного класса.

Доступ членов в классе по умолчанию является закрытым. Доступ членов в структуре или объединении по умолчанию является открытым.

Доступ базового класса по умолчанию является закрытым для классов и открытым для структур. Объединения не могут иметь базовые классы.

Для получения дополнительной информации [friend](../cpp/friend-cpp.md) [protected](../cpp/protected-cpp.md) [Controlling Access to Class Members](member-access-control-cpp.md) [см.](../cpp/private-cpp.md)

## <a name="clr-specific"></a>Специально для /clr

В типах CLR ключевые слова для спецификации доступа СЗ **(государственные,** **частные**и **защищенные)** могут влиять на видимость типов и методов в отношении сборок. Для получения дополнительной информации [см.](member-access-control-cpp.md)

> [!NOTE]
> Файлы, компилированные с [помощью /LN,](../build/reference/ln-create-msil-module.md) не подвержены такому поведению. В этом случае все управляемые классы (открытые или закрытые) будут видны.

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
[Keywords](../cpp/keywords-cpp.md)
