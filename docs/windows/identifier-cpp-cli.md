---
title: "__identifier (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__identifier"
  - "__identifier_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__identifier - ключевое слово [C++]"
ms.assetid: 348428af-afa7-4ff3-b571-acf874301cf2
caps.latest.revision: 18
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __identifier (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Позволяет использовать ключевые слова Visual C\+\+ в качестве идентификаторов.  
  
## Все платформы  
 **Синтаксис**  
  
```  
  
__identifier(  
Visual_C++_keyword  
)  
  
```  
  
 **Примечания**  
  
 Использование ключевого слова `__identifier` для идентификаторов, которые не являются ключевые словами, разрешено, но настоятельно не рекомендуется по причине стиля.  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
  
### Требования  
 Параметр компилятора: **\/ZW**  
  
### Примеры  
 **Пример**  
  
 В следующем примере создается класс в C\# с именем `template` и распространяется в виде библиотеки DLL.  В программе Visual C\+\+, использующей класс `template`, ключевое слово `__identifier` скрывает тот факт, что `template` является стандартным ключевым словом C\+\+.  
  
```  
// identifier_template.cs  
// compile with: /target:library  
public class template {  
   public void Run() { }  
}  
```  
  
```  
// keyword__identifier.cpp  
// compile with: /ZW  
#using <identifier_template.dll>  
int main() {  
   __identifier(template)^ pTemplate = ref new __identifier(template)();  
   pTemplate->Run();  
}  
```  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **Примечания**  
  
 Ключевое слово `__identifier` становится доступным при использовании параметров компилятора **\/clr** и **\/clr:oldSyntax**.  
  
### Требования  
 Параметр компилятора: **\/clr**  
  
### Примеры  
 **Пример**  
  
 В следующем примере создается класс в C\# с именем `template` и распространяется в виде библиотеки DLL.  В программе Visual C\+\+, использующей класс `template`, ключевое слово `__identifier` скрывает тот факт, что `template` является стандартным ключевым словом C\+\+.  
  
```  
// identifier_template.cs  
// compile with: /target:library  
public class template {  
   public void Run() { }  
}  
```  
  
```  
// keyword__identifier.cpp  
// compile with: /clr  
#using <identifier_template.dll>  
  
int main() {  
   __identifier(template) ^pTemplate = gcnew __identifier(template)();  
   pTemplate->Run();  
}  
```  
  
## См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)   
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)