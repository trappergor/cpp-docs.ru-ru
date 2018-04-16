---
title: Ошибка компилятора C2692 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C2692
dev_langs:
- C++
helpviewer_keywords:
- C2692
ms.assetid: 02ade3b4-b757-448b-b065-d7d71bc3f441
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9253bf70204bfded06189b6688405cabc43bdcf9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2692"></a>Ошибка компилятора C2692
«имя функции»: компилятора C необходимы полные прототипы функций "/ clr" параметр  
  
 При компиляции для .NET управляемый код, компилятор C требует объявления функций ANSI. Кроме того, если функция не принимает параметров, его необходимо явно объявить `void` типа параметра.