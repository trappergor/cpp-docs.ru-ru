---
title: private (C++)
ms.date: 11/04/2016
f1_keywords:
- private_cpp
helpviewer_keywords:
- private keyword [C++]
ms.assetid: 94e99983-46a5-4e21-800c-28f8a7c6a8ff
ms.openlocfilehash: d6dc1ca309c096a4f5e857ade3d7550749991f3f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366205"
---
# <a name="private-c"></a>private (C++)

## <a name="syntax"></a>Синтаксис

```
private:
   [member-list]
private base-class
```

## <a name="remarks"></a>Remarks

При предшествующем списке членов **класса, в частном** ключевом слове указывается, что эти участники доступны только от функций членов и друзей класса. Это применяется ко всем членам, объявленным до следующего описателя доступа или до конца класса.

При предшествующем названию базового **класса, в частном** ключевом слове указывается, что публичные и защищенные члены базового класса являются частными членами производного класса.

Доступ членов в классе по умолчанию является закрытым. Доступ членов в структуре или объединении по умолчанию является открытым.

Доступ базового класса по умолчанию является закрытым для классов и открытым для структур. Объединения не могут иметь базовые классы.

Для получения соответствующей [public](../cpp/public-cpp.md)информации [protected](../cpp/protected-cpp.md) [см.](../cpp/friend-cpp.md) [Controlling Access to Class Members](member-access-control-cpp.md)

## <a name="clr-specific"></a>Специально для /clr

В типах CLR ключевые слова для спецификации доступа СЗ **(государственные,** **частные**и **защищенные)** могут влиять на видимость типов и методов в отношении сборок. Для получения дополнительной информации [см.](member-access-control-cpp.md)

> [!NOTE]
> Файлы, компилированные с [помощью /LN,](../build/reference/ln-create-msil-module.md) не подвержены такому поведению. В этом случае все управляемые классы (открытые или закрытые) будут видны.

## <a name="end-clr-specific"></a>КОНЕЦ специально для /clr

## <a name="example"></a>Пример

```cpp
// keyword_private.cpp
class BaseClass {
public:
   // privMem accessible from member function
   int pubFunc() { return privMem; }
private:
   void privMem;
};

class DerivedClass : public BaseClass {
public:
   void usePrivate( int i )
      { privMem = i; }   // C2248: privMem not accessible
                         // from derived class
};

class DerivedClass2 : private BaseClass {
public:
   // pubFunc() accessible from derived class
   int usePublic() { return pubFunc(); }
};

int main() {
   BaseClass aBase;
   DerivedClass aDerived;
   DerivedClass2 aDerived2;
   aBase.privMem = 1;     // C2248: privMem not accessible
   aDerived.privMem = 1;  // C2248: privMem not accessible
                          //    in derived class
   aDerived2.pubFunc();   // C2247: pubFunc() is private in
                          //    derived class
}
```

## <a name="see-also"></a>См. также раздел

[Управление доступом к членам классов](member-access-control-cpp.md)<br/>
[Keywords](../cpp/keywords-cpp.md)
