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
ms.workload: cplusplus
ms.openlocfilehash: 15d76be8cdf9855435094d02be5bc28fe27fe89a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4049"></a>Предупреждение (уровень 1) C4049 компилятора
ограничение компилятора: завершение вывода номеров строк  
  
 Файл содержит более 16777215 (2<sup>24</sup>-1) исходных строк. Компилятор не нумерации 16777215.  
  
 Для кода после строки 16777215:  
  
-   Образ будет содержать сведения об отладке для номеров строк.  
  
-   Некоторые средства диагностики, может сообщаться неверные номера строк.  
  
-   Списки ASM (/ FAs) могут содержать неверные номера строк.