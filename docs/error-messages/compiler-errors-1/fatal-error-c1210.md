---
title: "Неустранимая ошибка C1210 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1210
dev_langs:
- C++
helpviewer_keywords:
- C1210
ms.assetid: e2208309-c284-425c-a7e8-48e96e66f35b
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: f3abd56aebdf7e83bbab10b6083ad6fc14987fbd
ms.lasthandoff: 02/24/2017

---
# <a name="fatal-error-c1210"></a>Неустранимая ошибка C1210
Параметры /clr:pure и /clr:safe не поддерживаются установленной версией среды выполнения  
  
 **/CLR: pure** и **/CLR: safe** параметры компилятора в Visual Studio 2015 являются устаревшими.  
  
 Ошибка C1210 возникает, когда компилятор из текущего выпуска используется со средой CLR из предыдущего выпуска.  
  
 Некоторые функциональные возможности компилятора могут не работать в предыдущей версии среды выполнения.  
  
 Чтобы устранить ошибку C1210, следует установить версию среды CLR, предназначенную для использования с компилятором.
