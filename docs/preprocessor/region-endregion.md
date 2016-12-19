---
title: "region, endregion | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.endregion"
  - "endregion_CPP"
  - "region_CPP"
  - "vc-pragma.region"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "прагма окончания региона"
  - "прагмы, окончание региона"
  - "прагмы, область"
  - "прагма региона"
ms.assetid: c697f807-622f-4796-851b-68a42bbecd84
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# region, endregion
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Директива **\#pragma region** позволяет указать блок кода, который можно разворачивать и сворачивать с помощью [функции структурирования](../Topic/Outlining.md) в редакторе кода Visual Studio.  
  
## Синтаксис  
  
```  
#pragma region name  
#pragma endregion comment  
```  
  
#### Параметры  
 `comment` \(необязательно\)  
 Комментарий, отображаемый в редакторе кода.  
  
 *имя* \(необязательно\)  
 Имя области.  Имя, отображаемое в редакторе кода.  
  
## Заметки  
 Директива **\#pragma endregion** обозначает конец блока **\#pragma region**.  
  
 Блок `#region` должен заканчиваться директивой **\#pragma endregion**.  
  
## Пример  
  
```  
// pragma_directives_region.cpp  
#pragma region Region_1  
void Test() {}  
void Test2() {}  
void Test3() {}  
#pragma endregion Region_1  
  
int main() {}  
```  
  
## См. также  
 [Директивы Pragma и ключевое слово \_\_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)