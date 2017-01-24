---
title: "Проблемы версий, связанные с типами значений, вложенными в собственные типы (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__nogc type - объявление"
  - "__value - ключевое слово, проблемы при вложении"
ms.assetid: 0a3b1a43-39c6-4b52-be2f-1074690188aa
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Проблемы версий, связанные с типами значений, вложенными в собственные типы (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Рассмотрим подписанный с использованием строгого имени компонент, который используется для построения клиентской сборки.  Этот компонент содержит тип значений, который используется в клиенте в качестве типа члена собственного объединения, класса или массива.  Если в последующих версиях изменяется размер или структура типа значений, следует выполнить повторную компиляцию клиента.  
  
 Создайте файл ключа с помощью программы [sn.exe](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md) \(`sn -k mykey.snk`\).  
  
## Пример  
 Ниже приведен пример компонента:  
  
```  
// nested_value_types.cpp  
// compile with: /clr /LD  
using namespace System::Reflection;  
[assembly:AssemblyVersion("1.0.0.*"),   
assembly:AssemblyKeyFile("mykey.snk")];  
  
public value struct S {  
   int i;  
   void Test() {  
      System::Console::WriteLine("S.i = {0}", i);  
   }  
};  
```  
  
## Пример  
 В следующем примере описывается клиент:  
  
```  
// nested_value_types_2.cpp  
// compile with: /clr  
#using <nested_value_types.dll>  
  
struct S2 {  
   S MyS1, MyS2;  
};  
  
int main() {  
   S2 MyS2a, MyS2b;  
   MyS2a.MyS1.i = 5;  
   MyS2a.MyS2.i = 6;  
   MyS2b.MyS1.i = 10;  
   MyS2b.MyS2.i = 11;  
  
   MyS2a.MyS1.Test();  
   MyS2a.MyS2.Test();  
   MyS2b.MyS1.Test();  
   MyS2b.MyS2.Test();  
}  
```  
  
## Output  
  
```  
S.i = 5  
S.i = 6  
S.i = 10  
S.i = 11  
```  
  
### Комментарии  
 Однако если в файле nested\_value\_types.cpp добавить другой член к структуре `struct S` \(например `double d;`\) и выполнить компиляцию компонента без повторной компиляции клиента, возникает необработанное исключение типа <xref:System.IO.FileLoadException?displayProperty=fullName>.  
  
## См. также  
 [Управляемые типы](../Topic/Managed%20Types%20\(C++-CLI\).md)