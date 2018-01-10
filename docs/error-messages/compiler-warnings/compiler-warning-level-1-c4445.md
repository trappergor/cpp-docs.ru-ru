---
title: "Предупреждение (уровень 1) C4445 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4445
dev_langs: C++
helpviewer_keywords: C4445
ms.assetid: 535e92a0-ba08-4dfc-89b2-af2dcdd7caeb
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0e351d23d943d53cef3184a826fecc90c5a28359
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4445"></a>Предупреждение компилятора (уровень 1) C4445
function: в управляемом типе или типе WinRT виртуальный метод не может быть закрытым  
  
 Если виртуальная функция закрытая, у производного типа нет доступа к ней. Чтобы устранить эту ошибку, измените тип доступ виртуальной функции-члена на защищенный или общий.