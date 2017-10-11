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
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: a70b679d4add5fa4ad2904e3c0d103e1c8881280
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2919"></a>Ошибка компилятора C2919
type: операторы не могут напрямую использоваться на опубликованной поверхности типа WinRT.  
  
 Система с типом среды выполнения Windows не поддерживает функции — члены оператора на опубликованной поверхности типа. Это вызвано тем, что не все языки могут использовать функции — члены оператора. Вы можете создать закрытые или внутренние функции — члены оператора, которые можно вызывать из кода C++ в том же классе или блоке компиляции.  
  
 Чтобы устранить эту проблему, удалите функцию — член оператора из открытого интерфейса или измените ее на именованную функцию-член. Например, вместо `operator==` назовите функцию-член `Equals`.
