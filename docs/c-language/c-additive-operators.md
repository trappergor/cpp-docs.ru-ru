---
title: "Аддитивные операторы в C | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- usual arithmetic conversions
- operators [C], addition
- + operator, additive operators
- additive operators
- arithmetic operators [C++], additive operators
ms.assetid: bb8ac205-b061-41fc-8dd4-dab87c8b900c
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
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
translationtype: Human Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 885967baa9a7e3651dde02bb5cfb1d6b9783f42b
ms.lasthandoff: 04/01/2017

---
# <a name="c-additive-operators"></a>Аддитивные операторы в C
Аддитивные операторы выполняют сложение (**+**) и вычитание (**-**).  
  
## <a name="syntax"></a>Синтаксис  
 *additive-expression*:  
 *multiplicative-expression*  
  
 *additive-expression*  **+**  *multiplicative-expression*  
  
 *additive-expression*  **-**  *multiplicative-expression*  
  
> [!NOTE]
>  Хотя синтаксис *выражения-сложения* включает *выражение-умножения*, это не означает, что требуются выражения, в которых используется умножение. Синтаксис *выражения-умножения*, *выражения-приведения* и *унарного выражения* см. в документе [Краткие сведения о синтаксисе языка C](../c-language/c-language-syntax-summary.md).  
  
 Операнды могут быть целыми значениями или значениями с плавающей запятой. Некоторые аддитивные операции также можно выполнять со значениями указателя, как описано в разделах, посвященных каждому оператору.  
  
 Аддитивные операторы выполняют обычные арифметические преобразования с операндами целочисленного типа и типа с плавающей запятой. После преобразования тип результата совпадает с типом операндов. Поскольку преобразования, выполняемые аддитивными операторами, не обеспечивают условия переполнения или потери значимости, данные могут быть потеряны, если результат аддитивной операции невозможно представить в типе операндов после преобразования.  
  
## <a name="see-also"></a>См. также  
 [Аддитивные операторы: + и -](../cpp/additive-operators-plus-and.md)
