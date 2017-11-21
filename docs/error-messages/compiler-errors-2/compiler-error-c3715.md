---
title: "Ошибка компилятора C3715 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3715
dev_langs: C++
helpviewer_keywords: C3715
ms.assetid: ee5dce88-ddc4-4bdb-9464-47467ce1674f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0fcfe83ada2c55540562fc17189d693675326c81
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3715"></a>Ошибка компилятора C3715
«указатель»: должен быть указателем на «class»  
  
 Задан указатель в [__hook](../../cpp/hook.md) или [__unhook](../../cpp/unhook.md) , не указывающий на допустимый класс. Чтобы устранить эту ошибку, убедитесь, что ваш `__hook` и `__unhook` вызовах указывается указатели на допустимые классы.