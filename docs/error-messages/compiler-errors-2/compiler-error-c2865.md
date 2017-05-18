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
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 3bb55d094e00400c57617857aa1ac29677f1b72a
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2865"></a>Ошибка компилятора C2865
«функция»: недопустимое сравнение для дескриптора_или_указателя  
  
 Можно сравнить ссылки на [классы и структуры](../../windows/classes-and-structs-cpp-component-extensions.md) или управляемых ссылочных типов только на равенство, чтобы увидеть, если они ссылаются на один и тот же объект (==) или на разные объекты (! =).  
  
 Невозможно сравнить их для упорядочения, так как среда выполнения .NET может переместить управляемые объекты в любое время изменить результат теста.
