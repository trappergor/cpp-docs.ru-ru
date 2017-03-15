---
title: "Ошибка средств компоновщика LNK2004 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK2004
dev_langs:
- C++
helpviewer_keywords:
- LNK2004
ms.assetid: 07645371-e67b-4a2c-b0e0-dde24c94ef7e
caps.latest.revision: 7
author: corob-msft
ms.author: corob
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: f66c3eda90f3d0f9149d70418cb40f08b3b94df7
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-error-lnk2004"></a>Ошибка средств компоновщика LNK2004
Переполнение относительной адресной привязки gp к «целевому объекту»; краткая секция «секция» слишком велика или за пределы допустимого диапазона.  
  
 Секция слишком велика.  
  
 Чтобы устранить эту ошибку, уменьшить размер краткой секции, явным образом разместив данные в длинных секциях с помощью раздела #pragma («.sectionname», чтение, запись, long) и с помощью `__declspec(allocate(".sectionname"))` на объявления и определения данных.  Например:  
  
```  
#pragma section(".data$mylong", read, write, long)  
__declspec(allocate(".data$mylong"))  
char    rg0[1] = { 1 };  
char    rg1[2] = { 1 };  
char    rg2[4] = { 1 };  
char    rg3[8] = { 1 };  
char    rg4[16] = { 1 };  
char    rg5[32] = { 1 };  
```  
  
 Также можно переместить логически сгруппированные данные в отдельную структуру, это коллекция данных превышает 8 байт, выделяющими компилятор в разделе большие объемы данных.  Например:  
  
```  
// from this...  
int     w1  = 23;  
int     w2 = 46;  
int     w3 = 23*3;  
int     w4 = 23*4;  
  
// to this...  
struct X {  
    int     w1;  
    int     w2;  
    int     w3;  
    int     w4;  
} x  = { 23, 23*2, 23*3, 23*4 };  
  
```  
  
 Эта ошибка сопровождается неустранимой ошибки `LNK1165`.
