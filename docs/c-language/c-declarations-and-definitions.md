---
title: "Объявления и определения в C | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 575f0c9b-5554-4346-be64-b2129ca9227f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 526a7bb902374fb3df936d5ac81cf602e1871a4f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="c-declarations-and-definitions"></a>Объявления и определения в C
Объявление устанавливает связь между указанной переменной, функцией или типом и их атрибутами. В статье [Общие сведения об объявлениях](../c-language/overview-of-declarations.md) приводится синтаксис ANSI для нетерминального элемента `declaration`. В объявлении также определяется, где и когда возможен доступ к идентификатору ("компоновка" идентификатора). Дополнительные сведения о компоновке см. в статье [Время существования, область, видимость и компоновка](../c-language/lifetime-scope-visibility-and-linkage.md).  
  
 Определение переменной устанавливает те же связи, что и объявление, но также приводит к выделению памяти для переменной.  
  
 Например, функции `main`, `find` и `count` и переменные `var` и `val` определяются в одном исходном файле в следующем порядке:  
  
```  
int main() {}  
  
int var = 0;  
double val[MAXVAL];  
char find( fileptr ) {}  
int count( double f ) {}  
```  
  
 Переменные `var` и `val` могут использоваться в функциях `find` и `count`; никакие дополнительные объявления не требуются. Однако в функции `main` эти имена не видны (доступ к ним невозможен).  
  
## <a name="see-also"></a>См. также  
 [Файлы с исходным кодом и исходные программы](../c-language/source-files-and-source-programs.md)