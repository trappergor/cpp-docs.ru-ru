---
title: Неустранимая ошибка C1211 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1211
dev_langs:
- C++
helpviewer_keywords:
- C1211
ms.assetid: df0ca70d-ec6e-4400-926a-b877e2599978
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4ef92816c157d6bbc72d7c7539f2d0644c70082b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1211"></a>Неустранимая ошибка C1211
Пользовательский атрибут TypeForwardedTo не поддерживается установленной версией среды выполнения  
  
 Ошибка C1211 возникает, когда компилятор из текущего выпуска используется со средой CLR из предыдущего выпуска.  
  
 Некоторые функциональные возможности компилятора могут не работать в предыдущей версии среды выполнения.  
  
 Чтобы устранить ошибку C1211, установите среду CLR, поставляемую вместе с используемым компилятором.  
  
 Дополнительные сведения см. в разделе [переадресации типов (C + +/ CLI)](../../windows/type-forwarding-cpp-cli.md).