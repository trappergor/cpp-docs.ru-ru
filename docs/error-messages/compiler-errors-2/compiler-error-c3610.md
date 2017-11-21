---
title: "Ошибка компилятора C3610 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3610
dev_langs: C++
helpviewer_keywords: C3610
ms.assetid: 9349a348-9d37-4a00-9eab-481039268d31
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0cacac87535864c6268d0f078566b9ab224e9151
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3610"></a>Ошибка компилятора C3610
«тип_значения»: тип значения должен быть «упакован» перед вызовом метода «метод» может быть  
  
 По умолчанию тип значения не в управляемой куче. Перед вызовом методов из классов среды выполнения .NET, такие как `Object`, необходимо переместить тип значения в управляемую кучу.  
  
 C3610 доступен только с помощью параметра компилятора устаревшие **/CLR: oldSyntax**.  
