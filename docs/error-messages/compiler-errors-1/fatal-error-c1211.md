---
title: Неустранимая ошибка C1211 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- C1211
dev_langs:
- C++
helpviewer_keywords:
- C1211
ms.assetid: df0ca70d-ec6e-4400-926a-b877e2599978
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a57418d53626aefa1b9616b2790bd23e0a2d941e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1211"></a>Неустранимая ошибка C1211
Пользовательский атрибут TypeForwardedTo не поддерживается установленной версией среды выполнения  
  
 Ошибка C1211 возникает, когда компилятор из текущего выпуска используется со средой CLR из предыдущего выпуска.  
  
 Некоторые функциональные возможности компилятора могут не работать в предыдущей версии среды выполнения.  
  
 Чтобы устранить ошибку C1211, установите среду CLR, поставляемую вместе с используемым компилятором.  
  
 Дополнительные сведения см. в разделе [переадресации типов (C + +/ CLI)](../../windows/type-forwarding-cpp-cli.md).