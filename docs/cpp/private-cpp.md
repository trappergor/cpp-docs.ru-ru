---
title: Private (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- private_cpp
dev_langs:
- C++
helpviewer_keywords:
- private keyword [C++]
ms.assetid: 94e99983-46a5-4e21-800c-28f8a7c6a8ff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 20d064a1154126878ce75d9dd08d88fa9d65f83c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46028562"
---
# <a name="private-c"></a>private (C++)

## <a name="syntax"></a>Синтаксис

```
private:
   [member-list]
private base-class
```

## <a name="remarks"></a>Примечания

Когда располагается перед списком членов класса, **частного** ключевое слово указывает, что эти члены доступны только из функции-члены и дружественные элементы класса. Это применяется ко всем членам, объявленным до следующего описателя доступа или до конца класса.

Если перед именем базового класса, **частного** ключевое слово указывает, что открытые и защищенные члены базового класса являются закрытыми членами производного класса.

Доступ членов в классе по умолчанию является закрытым. Доступ членов в структуре или объединении по умолчанию является открытым.

Доступ базового класса по умолчанию является закрытым для классов и открытым для структур. Объединения не могут иметь базовые классы.

Дополнительные сведения см. в разделе [friend](../cpp/friend-cpp.md), [открытый](../cpp/public-cpp.md), [защищенные](../cpp/protected-cpp.md)и в таблице членского доступа в [управление доступом к членам класса](member-access-control-cpp.md).

## <a name="clr-specific"></a>Специально для /clr

В CLR-типах ключевые слова описателя доступа C++ (**открытый**, **частного**, и **защищенные**) может повлиять на видимость типов и методов с точки зрения сборок. Дополнительные сведения см. в разделе [управление доступом к членам](member-access-control-cpp.md).

> [!NOTE]
>  Файлы, скомпилированные с помощью [/LN](../build/reference/ln-create-msil-module.md) не затрагиваются этим поведением. В этом случае все управляемые классы (открытые или закрытые) будут видны.

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

## <a name="see-also"></a>См. также

[Управление доступом к членам классов](member-access-control-cpp.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)