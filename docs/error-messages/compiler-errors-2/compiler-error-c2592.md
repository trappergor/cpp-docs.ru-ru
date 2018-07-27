---
title: Ошибка компилятора C2592 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2592
dev_langs:
- C++
helpviewer_keywords:
- C2592
ms.assetid: 833a4d7b-66ef-4d4c-ae83-a533c2b0eb07
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5d999056d718d9c7aad93d08a99895caebbef539
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33229817"
---
# <a name="compiler-error-c2592"></a>Ошибка компилятора C2592
class: base_class_2 наследуется от base_class_1 и не может быть указан повторно  
  
 Можно указать только базовые классы, которые не наследуют от других базовых классов. В данном случае в описании `class` требуется только `base_class_1`, так как `base_class_1` уже наследует `base_class_2`.