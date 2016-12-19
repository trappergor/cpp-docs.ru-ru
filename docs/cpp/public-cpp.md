---
title: "public (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "public"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "public - ключевое слово [C++]"
ms.assetid: f3e10a59-39f6-4bcd-827e-3e99f8f89497
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# public (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Синтаксис  
  
```  
public:  
   [member-list]  
public base-class  
```  
  
## Заметки  
 Если ключевое слово **public** располагается перед списком членов класса, оно указывает, что эти члены доступны из любой функции.  Это применяется ко всем членам, объявленным до следующего описателя доступа или до конца класса.  
  
 Если ключевое слово **public** располагается перед именем базового класса, оно указывает, что открытые и защищенные члены базового класса являются, соответственно, открытыми и защищенными членами производного класса.  
  
 Доступ членов в классе по умолчанию является закрытым.  Доступ членов в структуре или объединении по умолчанию является открытым.  
  
 Доступ базового класса по умолчанию является закрытым для классов и открытым для структур.  Объединения не могут иметь базовые классы.  
  
 Дополнительные сведения см. в разделах [private](../Topic/private%20\(C++\).md), [protected](../Topic/protected%20\(C++\).md) и [friend](../cpp/friend-cpp.md), а также в таблице доступа к членам в разделе [Управление доступом к членам класса](../misc/controlling-access-to-class-members.md).  
  
## Специально для \/clr  
 В CLR\-типах ключевые слова описателя доступа C\+\+ \(**public**, `private` и `protected`\) могут повлиять на видимость типов и методов с точки зрения сборок.  Дополнительные сведения см. в статье [Видимость типов и членов](../Topic/Type%20and%20Member%20Visibility.md).  
  
> [!NOTE]
>  Файлы, скомпилированные с параметром [\/LN](../build/reference/ln-create-msil-module.md), не затронуты этим поведением.  В этом случае все управляемые классы \(открытые или закрытые\) будут видны.  
  
## КОНЕЦ специально для \/clr  
  
## Пример  
  
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
  
## См. также  
 [Управление доступом к членам классов](../misc/controlling-access-to-class-members.md)   
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)