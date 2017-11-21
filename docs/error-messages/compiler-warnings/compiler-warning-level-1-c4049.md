---
title: "Предупреждение (уровень 1) C4049 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4049
dev_langs: C++
helpviewer_keywords: C4049
ms.assetid: d11c1870-bcfc-4d71-8945-b87ec6ec3514
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6e749571bcf4c0e1547279a857e50556f766c576
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4049"></a>Предупреждение (уровень 1) C4049 компилятора
ограничение компилятора: завершение вывода номеров строк  
  
 Файл содержит более 16777215 (2<sup>24</sup>-1) исходных строк. Компилятор не нумерации 16777215.  
  
 Для кода после строки 16777215:  
  
-   Образ будет содержать сведения об отладке для номеров строк.  
  
-   Некоторые средства диагностики, может сообщаться неверные номера строк.  
  
-   Списки ASM (/ FAs) могут содержать неверные номера строк.