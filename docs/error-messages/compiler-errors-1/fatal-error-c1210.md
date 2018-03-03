---
title: "Неустранимая ошибка C1210 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1210
dev_langs:
- C++
helpviewer_keywords:
- C1210
ms.assetid: e2208309-c284-425c-a7e8-48e96e66f35b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c11ed9df47ae7fc607189683b52a35779e485996
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1210"></a>Неустранимая ошибка C1210
Параметры /clr:pure и /clr:safe не поддерживаются установленной версией среды выполнения  
  
 Параметры компилятора **/CLR: pure** и **/CLR: safe** в Visual Studio 2015 не рекомендуется использовать.  
  
 Ошибка C1210 возникает, когда компилятор из текущего выпуска используется со средой CLR из предыдущего выпуска.  
  
 Некоторые функциональные возможности компилятора могут не работать в предыдущей версии среды выполнения.  
  
 Чтобы устранить ошибку C1210, следует установить версию среды CLR, предназначенную для использования с компилятором.