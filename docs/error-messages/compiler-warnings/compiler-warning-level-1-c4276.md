---
title: "Предупреждение (уровень 1) C4276 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4276
dev_langs:
- C++
helpviewer_keywords:
- C4276
ms.assetid: 9d738c2d-29e5-408a-b9ff-be1a850b2238
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: af9a32da86a0ea9e530af03a2175976d4cd9f091
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4276"></a>Предупреждение компилятора (уровень 1) C4276
«функция»: не предоставлен прототип; предполагается отсутствие параметров  
  
 При получении адреса функции с [__stdcall](../../cpp/stdcall.md) соглашение о вызовах, вы должны предоставить прототип, чтобы компилятор может создать внутреннее имя функции. Поскольку *функция* не имеет прототипа, компилятор, при создании декорированного имени, предполагается функция не имеет параметров.