---
title: "Предупреждение (уровень 4) C4714 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4714
dev_langs:
- C++
helpviewer_keywords:
- C4714
ms.assetid: 22c7fd0c-899d-4e9b-95f3-725b2c49fb46
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5d49ff1bbf6538965d277b0afdd6c96fd9c71ef0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4714"></a>Предупреждение компилятора (уровень 4) C4714
функция «функция», помеченная как __forceinline, не является встроенной  
  
 Данная функция была выбрана для подстановки, но компилятор не выполняет встраивание.  
  
 Несмотря на то что `__forceinline` является сильным указанием компилятору, чем `__inline`, встраивание выполняется на усмотрение компилятора, но эвристики для определения преимуществ встраивания этой функции.  
  
 В некоторых случаях компилятор выполняет встроенную определенных функций по техническим причинам. Например компилятор не будет подставлять:  
  
-   Функция, если это привело бы к смешивание SEH и C++ EH.  
  
-   Некоторые функции с копиями созданных объектов, переданных по значению при включенном - GX/EHs/EHa.  
  
-   Функции, возвращающие объект удаляемых по значению, если включена - GX/EHs/EHa.  
  
-   Функции со встроенной сборкой при компилировании без параметров - Og/Ox/O1/O2.  
  
-   Функции с переменное число аргументов.  
  
-   Функция с **повторите** инструкции (обработка исключений с ++).  
  
 Следующий пример приводит к возникновению ошибки C4714:  
  
```  
// C4714.cpp  
// compile with: /Ob1 /GX /W4  
__forceinline void func1()  
{  
   try  
   {  
   }  
   catch (...)  
   {  
   }  
}  
  
void func2()  
{  
   func1();   // C4714  
}  
  
int main()  
{  
}  
```