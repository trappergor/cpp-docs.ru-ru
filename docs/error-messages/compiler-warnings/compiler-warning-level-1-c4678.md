---
title: Предупреждение компилятора предупреждение (уровень 1) C4678 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4678
dev_langs:
- C++
helpviewer_keywords:
- C4678
ms.assetid: 0c588f34-595d-4e5c-9470-8723fca2cc06
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 73871d69198752e12a629d441982c2da47146517
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4678"></a>Предупреждение компилятора (уровень 1) C4678
базовый класс "базовый_тип" менее доступен, чем "производный_тип"  
  
Открытый тип является производным от закрытого типа. Если экземпляр открытого типа создается в связанной сборке, то члены закрытого базового типа будут недоступны.  
  
Предупреждение C4678 доступен только с помощью параметра компилятора устаревшие **/CLR: oldSyntax**. Считается ошибкой при использовании **/CLR**наличие базового класса, менее доступного, производный от него класс.  
