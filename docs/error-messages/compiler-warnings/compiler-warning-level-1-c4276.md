---
title: Предупреждение (уровень 1) C4276 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4276
dev_langs:
- C++
helpviewer_keywords:
- C4276
ms.assetid: 9d738c2d-29e5-408a-b9ff-be1a850b2238
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: afedab27c2fb93075aa33053c12ec6973824f144
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4276"></a>Предупреждение компилятора (уровень 1) C4276
«функция»: не предоставлен прототип; предполагается отсутствие параметров  
  
 При получении адреса функции с [__stdcall](../../cpp/stdcall.md) соглашение о вызовах, вы должны предоставить прототип, чтобы компилятор может создать внутреннее имя функции. Поскольку *функция* не имеет прототипа, компилятор, при создании декорированного имени, предполагается функция не имеет параметров.