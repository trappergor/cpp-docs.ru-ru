---
title: Неустранимая ошибка NMAKE U1045 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1045
dev_langs:
- C++
helpviewer_keywords:
- U1045
ms.assetid: dc70d162-14b9-4107-9237-7514044d72e3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 673b20dde7156025c6aa56c487433eebe9e77aa3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33316378"
---
# <a name="nmake-fatal-error-u1045"></a>Неустранимая ошибка NMAKE U1045
ошибка создания : сообщение  
  
 Сбой программы или команды, вызванной NMAKE, по указанной причине. Когда NMAKE вызывает другую программу, например, компилятор или компоновщик, вызов может окончиться сбоем или же вызванная программа может возвратить ошибку. Это сообщение используется для передачи информации об ошибке.  
  
 Чтобы устранить эту проблему, сначала определите причину ошибки. Можно использовать команды, отображаемые с помощью параметра NMAKE [/N](../../build/nmake-options.md) переключатель, чтобы проверить параметры среды и повторить действия, выполненные NMAKE в командной строке.