---
title: Ошибка компилятора ресурсов RC2151 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC2151
dev_langs:
- C++
helpviewer_keywords:
- RC2151
ms.assetid: 3c47e535-c78d-4338-aab9-9b47e2c34728
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8349aa14de6aec96fa1b526cbcffbe79036f804d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33323476"
---
# <a name="resource-compiler-error-rc2151"></a>Ошибка компилятора ресурсов RC2151
Невозможно повторно использовать строковые константы  
  
 Вы используете то же значение дважды в **STRINGTABLE** инструкции. Убедитесь, что вы нет смешанного сочетания десятичных и шестнадцатеричных значений.  
  
 Каждый идентификатор в **STRINGTABLE** должно быть уникальным. Для максимальной эффективности используйте зависимые константы, начинающиеся на нескольких 16.