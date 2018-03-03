---
title: "Ошибка компилятора C2865 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2865
dev_langs:
- C++
helpviewer_keywords:
- C2865
ms.assetid: 973eb6a0-c99a-4d25-b3e5-fe0539794d77
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 149ca019ef30d66dba63bc927d79064a269d8c70
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2865"></a>Ошибка компилятора C2865
«функция»: недопустимое сравнение для дескриптора_или_указателя  
  
 Вы можете сравнить ссылки на [классы и структуры](../../windows/classes-and-structs-cpp-component-extensions.md) или управляемых типов ссылку только на равенство для просмотра, если они ссылаются на один и тот же объект (==) или на разные объекты (! =).  
  
 Невозможно сравнить их для упорядочивания, так как среда выполнения .NET может переместить управляемых объектов в любое время изменить результат теста.