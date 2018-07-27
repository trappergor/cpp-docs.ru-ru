---
title: Ошибка компилятора C2919 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2919
dev_langs:
- C++
helpviewer_keywords:
- C2919
ms.assetid: 140a6db9-eb48-4c5e-84a7-a09d2653605b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c5e2eb2a32f1a906814f5b347ba1ebf13eba71ff
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33245806"
---
# <a name="compiler-error-c2919"></a>Ошибка компилятора C2919
type: операторы не могут напрямую использоваться на опубликованной поверхности типа WinRT.  
  
 Система с типом среды выполнения Windows не поддерживает функции — члены оператора на опубликованной поверхности типа. Это вызвано тем, что не все языки могут использовать функции — члены оператора. Вы можете создать закрытые или внутренние функции — члены оператора, которые можно вызывать из кода C++ в том же классе или блоке компиляции.  
  
 Чтобы устранить эту проблему, удалите функцию — член оператора из открытого интерфейса или измените ее на именованную функцию-член. Например, вместо `operator==` назовите функцию-член `Equals`.