---
title: Предупреждение (уровень 4) C4611 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4611
dev_langs:
- C++
helpviewer_keywords:
- C4611
ms.assetid: bd90d0a6-75f9-4e97-968d-dda6773e9fd8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5946c10b5e0e0e7e08f1ee37c77120896937adb1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33293157"
---
# <a name="compiler-warning-level-4-c4611"></a>Предупреждение компилятора (уровень 4) C4611
взаимодействие между «функция» и деструктором объектов C++ не будет переносимым  
  
 На некоторых платформах функции, включающие **перехватывать** может не поддерживают семантику объекта C++ уничтожения при работе вне области видимости.  
  
 Чтобы избежать непредсказуемого поведения, избегайте использования **перехватывать** в функциях, имеющих конструкторы и деструкторы.  
  
 Это предупреждение выдается только один раз; в разделе [в директиве pragma warning](../../preprocessor/warning.md).