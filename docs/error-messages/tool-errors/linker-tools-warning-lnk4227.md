---
title: "Предупреждение средств компоновщика LNK4227 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4227"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4227"
ms.assetid: 941a0414-9964-4e02-8487-f9daa42ef7f9
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Предупреждение средств компоновщика LNK4227
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

предупреждение операции с метаданными \(HRESULT\) : предупреждающее\_сообщение  
  
 Компоновщик обнаружил различия в метаданных при слиянии:  
  
-   одной или нескольких сборок, на которые имеются ссылки, со сборкой, построение которой выполняется в текущий момент;  
  
-   одного или нескольких файлов исходного кода в компиляции.  
  
 Например, предупреждение LNK4227 может появиться при наличии двух глобальных функций с одинаковыми именами, но с разными параметрами \(объявления не являются согласованными во всех единицах компиляции\).  Увидеть различия этих типов можно, применив команду ildasm.exe \/TEXT \/METADATA `object_file` для каждого OBJ\-файла.  
  
 Предупреждение LNK4227 также сообщает о проблемах, инициированных другим инструментом.  Например, это может быть программа al.exe; дополнительные сведения см. в разделе [Ошибки и предупреждения программы Al.exe](http://msdn.microsoft.com/ru-ru/7f125d49-0a03-47a6-9ba9-d61a679a7d4b).  
  
 Чтобы устранить это предупреждение, необходимо разрешить проблемы с метаданными.  
  
 Например, предупреждение LNK4227 возникает, когда сборка, на которую есть ссылка, и сборка, ссылающаяся на нее, подписаны по\-разному.  
  
 Следующий пример приводит к возникновению ошибки LNK4227:  
  
```  
// LNK4227.cpp  
// compile with: /clr  
using namespace System::Reflection;  
  
[assembly:AssemblyDelaySignAttribute(false)];  
  
int main() {}  
```  
  
 а затем  
  
```  
// LNK4227b.cpp  
// compile with: /clr LNK4227.cpp /FeLNK4227b.exe  
using namespace System::Reflection;  
using namespace System::Runtime::CompilerServices;  
  
[assembly:AssemblyDelaySignAttribute(true)];  
// Try the following line instead  
// [assembly:AssemblyDelaySignAttribute(false)];  
  
ref class MyClass  
{  
};  
```  
  
 Следующий пример приводит к возникновению ошибки LNK4227:  
  
```  
// LNK4227c.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System::Reflection;  
  
[assembly:AssemblyDelaySignAttribute(false)];  
  
int main() {}  
```  
  
 а затем  
  
```  
// LNK4227d.cpp  
// compile with: /clr:oldSyntax LNK4227c.cpp /FeLNK4227d.exe  
#using <mscorlib.dll>  
using namespace System::Reflection;  
using namespace System::Runtime::CompilerServices;  
  
[assembly:AssemblyDelaySignAttribute(true)];  
  
__gc class MyClass  
{  
};  
```  
  
 Предупреждение LNK4227 также может возникать, когда в атрибуты сборки передаются номера версий в неправильном формате.  Синтаксис с использованием "\*" применим только к атрибуту AssemblyVersionAttribute.  Чтобы устранить это предупреждение, в других атрибутах версий, отличных от AssemblyVersionAttribute, необходимо использовать только цифры.  
  
 Следующий пример приводит к возникновению ошибки LNK4227:  
  
```  
// LNK4227e.cpp  
// compile with: /clr /LD /W1  
using namespace System::Reflection;  
[assembly:AssemblyVersionAttribute("2.3.*")];   // OK  
[assembly:AssemblyFileVersionAttribute("2.3.*")];   // LNK4227  
// try the following line instead  
// [assembly:AssemblyFileVersionAttribute("2.3")];  
```