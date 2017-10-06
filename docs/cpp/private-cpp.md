---
title: "закрытый (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- private_cpp
dev_langs:
- C++
helpviewer_keywords:
- private keyword [C++]
ms.assetid: 94e99983-46a5-4e21-800c-28f8a7c6a8ff
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: ec12850b2d2059c2824c0585edee21cb3fd1a7f7
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="private-c"></a>private (C++)
## <a name="syntax"></a>Синтаксис  
  
```  
private:  
   [member-list]  
private base-class  
```  
  
## <a name="remarks"></a>Примечания  
 Если ключевое слово `private` располагается перед списком членов класса, оно указывает, что эти члены доступны только в функциях-членах и дружественных объектах класса. Это применяется ко всем членам, объявленным до следующего описателя доступа или до конца класса.  
  
 Если ключевое слово `private` располагается перед именем базового класса, оно указывает, что открытые и защищенные члены базового класса являются закрытыми членами производного класса.  
  
 Доступ членов в классе по умолчанию является закрытым. Доступ членов в структуре или объединении по умолчанию является открытым.  
  
 Доступ базового класса по умолчанию является закрытым для классов и открытым для структур. Объединения не могут иметь базовые классы.  
  
 Дополнительные сведения см. в разделе [friend](../cpp/friend-cpp.md), [открытый](../cpp/public-cpp.md), [защищенных](../cpp/protected-cpp.md)и таблица доступ к членам в [управление доступом к членам класса](member-access-control-cpp.md).  
  
## <a name="clr-specific"></a>Специально для /clr  
 В CLR-типах ключевые слова описателя доступа C++ (**открытый**, `private`, и `protected`) может повлиять на видимость типов и методов с точки зрения сборок. Дополнительные сведения см. в разделе [управление доступом к членам](member-access-control-cpp.md).  
  
> [!NOTE]
>  Файлы, скомпилированные с [/LN](../build/reference/ln-create-msil-module.md) не затронуты этим поведением. В этом случае все управляемые классы (открытые или закрытые) будут видны.  
  
## <a name="end-clr-specific"></a>КОНЕЦ специально для /clr  
  
## <a name="example"></a>Пример  
  
```  
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
 [Управление доступом к членам класса](member-access-control-cpp.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)
