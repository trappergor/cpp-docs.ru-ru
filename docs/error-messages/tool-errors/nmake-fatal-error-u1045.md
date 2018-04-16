---
title: Неустранимая ошибка NMAKE U1045 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- U1045
dev_langs:
- C++
helpviewer_keywords:
- U1045
ms.assetid: dc70d162-14b9-4107-9237-7514044d72e3
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cdd9fb3d0bcee20e1952cea6444f586a9117365a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-fatal-error-u1045"></a>Неустранимая ошибка NMAKE U1045
ошибка создания : сообщение  
  
 Сбой программы или команды, вызванной NMAKE, по указанной причине. Когда NMAKE вызывает другую программу, например, компилятор или компоновщик, вызов может окончиться сбоем или же вызванная программа может возвратить ошибку. Это сообщение используется для передачи информации об ошибке.  
  
 Чтобы устранить эту проблему, сначала определите причину ошибки. Можно использовать команды, отображаемые с помощью параметра NMAKE [/N](../../build/nmake-options.md) переключатель, чтобы проверить параметры среды и повторить действия, выполненные NMAKE в командной строке.