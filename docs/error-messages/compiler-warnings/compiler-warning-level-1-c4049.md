---
title: Предупреждение (уровень 1) C4049 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4049
dev_langs:
- C++
helpviewer_keywords:
- C4049
ms.assetid: d11c1870-bcfc-4d71-8945-b87ec6ec3514
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1eea293ff64ed8fe2bf4bf0d38d897eb82223802
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4049"></a>Предупреждение (уровень 1) C4049 компилятора
ограничение компилятора: завершение вывода номеров строк  
  
 Файл содержит более 16777215 (2<sup>24</sup>-1) исходных строк. Компилятор не нумерации 16777215.  
  
 Для кода после строки 16777215:  
  
-   Образ будет содержать сведения об отладке для номеров строк.  
  
-   Некоторые средства диагностики, может сообщаться неверные номера строк.  
  
-   Списки ASM (/ FAs) могут содержать неверные номера строк.