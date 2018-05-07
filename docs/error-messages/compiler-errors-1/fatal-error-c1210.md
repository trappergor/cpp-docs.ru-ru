---
title: Неустранимая ошибка C1210 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1210
dev_langs:
- C++
helpviewer_keywords:
- C1210
ms.assetid: e2208309-c284-425c-a7e8-48e96e66f35b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: df1b970454af8ab692aea949d437e4c1cce4e0cb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1210"></a>Неустранимая ошибка C1210
Параметры /clr:pure и /clr:safe не поддерживаются установленной версией среды выполнения  
  
 Параметры компилятора **/CLR: pure** и **/CLR: safe** в Visual Studio 2015 не рекомендуется использовать.  
  
 Ошибка C1210 возникает, когда компилятор из текущего выпуска используется со средой CLR из предыдущего выпуска.  
  
 Некоторые функциональные возможности компилятора могут не работать в предыдущей версии среды выполнения.  
  
 Чтобы устранить ошибку C1210, следует установить версию среды CLR, предназначенную для использования с компилятором.