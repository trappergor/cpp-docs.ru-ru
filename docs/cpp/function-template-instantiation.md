---
title: "Создание экземпляра шаблона функции | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "шаблоны функций, создание экземпляра"
  - "создание экземпляра, шаблоны функций"
  - "шаблоны, создание экземпляра"
ms.assetid: f22a07c7-3ad1-465a-84f5-8737e274bd47
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Создание экземпляра шаблона функции
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

При первом вызове шаблона функции для каждого типа компилятор создает экземпляр.  Каждый экземпляр представляет собой шаблонную функцию, специализированную для данного типа.  Этот экземпляр будет вызваться каждый раз, когда функция используется для данного типа.  Если имеется несколько одинаковых экземпляров, даже в различных модулях, в исполняемый файл будет помещен только один экземпляр.  
  
 В шаблонах функций преобразование аргументов функции разрешается для любых пар аргументов и параметров, в которых параметр не зависит от аргумента шаблона.  
  
 Можно явно создавать экземпляры шаблонов функций, объявляя шаблон с определенным типом в качестве аргумента.  Например, приведенный ниже код допустим:  
  
```  
// function_template_instantiation.cpp  
template<class T> void f(T) { }  
  
// Instantiate f with the explicitly specified template.  
// argument 'int'  
//  
template void f<int> (int);  
  
// Instantiate f with the deduced template argument 'char'.  
template void f(char);  
int main()  
{  
}  
```  
  
## См. также  
 [Шаблоны функций](../cpp/function-templates.md)