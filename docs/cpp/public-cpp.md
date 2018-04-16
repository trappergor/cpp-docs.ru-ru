---
title: Public (C++) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- public_cpp
dev_langs:
- C++
helpviewer_keywords:
- public keyword [C++]
ms.assetid: f3e10a59-39f6-4bcd-827e-3e99f8f89497
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0ff41d2b12f43deabd82538a3e2fb10eb35ead16
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="public-c"></a>public (C++)
## <a name="syntax"></a>Синтаксис  
  
```  
public:  
   [member-list]  
public base-class  
```  
  
## <a name="remarks"></a>Примечания  
 Если перед списком членов класса **открытый** ключевое слово указывает, что эти члены доступны из любой функции. Это применяется ко всем членам, объявленным до следующего описателя доступа или до конца класса.  
  
 Если перед именем базового класса **открытый** ключевое слово указывает, что открытые и защищенные члены базового класса являются открытыми и защищенные члены, соответственно, производного класса.  
  
 Доступ членов в классе по умолчанию является закрытым. Доступ членов в структуре или объединении по умолчанию является открытым.  
  
 Доступ базового класса по умолчанию является закрытым для классов и открытым для структур. Объединения не могут иметь базовые классы.  
  
 Дополнительные сведения см. в разделе [закрытый](../cpp/private-cpp.md), [защищенных](../cpp/protected-cpp.md), [friend](../cpp/friend-cpp.md)и таблица доступ к членам в [управление доступом к членам класса](member-access-control-cpp.md) .  
  
## <a name="clr-specific"></a>Специально для /clr  
 В CLR-типах ключевые слова описателя доступа C++ (**открытый**, `private`, и `protected`) может повлиять на видимость типов и методов с точки зрения сборок. Дополнительные сведения см. в разделе [управление доступом к членам](member-access-control-cpp.md).  
  
> [!NOTE]
>  Файлы, скомпилированные с [/LN](../build/reference/ln-create-msil-module.md) не затронуты этим поведением. В этом случае все управляемые классы (открытые или закрытые) будут видны.  
  
## <a name="end-clr-specific"></a>КОНЕЦ специально для /clr  
  
## <a name="example"></a>Пример  
  
```  
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
  
## <a name="see-also"></a>См. также  
 [Управление доступом к членам класса](member-access-control-cpp.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)