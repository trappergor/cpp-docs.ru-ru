---
title: Ошибка компилятора C2692 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2692
dev_langs:
- C++
helpviewer_keywords:
- C2692
ms.assetid: 02ade3b4-b757-448b-b065-d7d71bc3f441
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a02110750a748b5c520df7d202a87957f227a802
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33231000"
---
# <a name="compiler-error-c2692"></a>Ошибка компилятора C2692
«имя функции»: компилятора C необходимы полные прототипы функций "/ clr" параметр  
  
 При компиляции для .NET управляемый код, компилятор C требует объявления функций ANSI. Кроме того, если функция не принимает параметров, его необходимо явно объявить `void` типа параметра.