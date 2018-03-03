---
title: "Ошибка компилятора C2919 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2919
dev_langs:
- C++
helpviewer_keywords:
- C2919
ms.assetid: 140a6db9-eb48-4c5e-84a7-a09d2653605b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4e2bde12c4c6ffa94f55e9dd205c3132a755ad94
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2919"></a>Ошибка компилятора C2919
type: операторы не могут напрямую использоваться на опубликованной поверхности типа WinRT.  
  
 Система с типом среды выполнения Windows не поддерживает функции — члены оператора на опубликованной поверхности типа. Это вызвано тем, что не все языки могут использовать функции — члены оператора. Вы можете создать закрытые или внутренние функции — члены оператора, которые можно вызывать из кода C++ в том же классе или блоке компиляции.  
  
 Чтобы устранить эту проблему, удалите функцию — член оператора из открытого интерфейса или измените ее на именованную функцию-член. Например, вместо `operator==` назовите функцию-член `Equals`.