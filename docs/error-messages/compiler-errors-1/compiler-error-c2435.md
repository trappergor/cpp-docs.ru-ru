---
title: "Ошибка компилятора C2435 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2435
dev_langs:
- C++
helpviewer_keywords:
- C2435
ms.assetid: be6aa8f8-579b-42ea-bdd8-2d01393646ad
caps.latest.revision: 12
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
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: dbc2045eae70cacd42e13ddb7cc8ecb3d60b8596
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2435"></a>Ошибка компилятора C2435
«переменная»: динамическая инициализация требует управляемую библиотеку CRT, нельзя компилировать при помощи/CLR: safe  
  
 **/CLR: pure** и **/CLR: safe** параметры компилятора в Visual Studio 2015 являются устаревшими.  
  
 Инициализация глобальных локальных переменных — приложения библиотеки CRT, скомпилированной с `/clr:pure`, не создает образов с возможностью проверки.  
  
 Дополнительные сведения см. в разделе [appdomain](../../cpp/appdomain.md) и [процесс](../../cpp/process.md).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2435:  
  
```  
// C2435.cpp  
// compile with: /clr:safe /c  
int globalvar = 0;   // C2435  
  
__declspec(process)  
int globalvar2 = 0;  
```
