---
title: "Ошибка построения проекта PRJ0025 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: PRJ0025
dev_langs: C++
helpviewer_keywords: PRJ0025
ms.assetid: 57725c78-bc63-44f3-9667-2969b2d7c41d
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8f99a57439e87e1841555c90326072ba1667b6b5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="project-build-error-prj0025"></a>Ошибка построения проекта PRJ0025
Пакетный файл «файл», содержащий знаки Юникода, не может быть преобразована в кодовую страницу ANSI пользователя.  
  
 ***Содержимое файла в кодировке Юникод***  
  
 Система проектов найти содержимое в кодировке Юникод в пользовательское правило сборки или сборки события, которое не может правильно преобразован в текущую кодовую страницу ANSI пользователя.  
  
 Способ устранения этой ошибки является обновления содержимого правила построения или события использовать ANSI, а также установите кодовую страницу на компьютере и установить его по умолчанию системы сборки.  
  
 Дополнительные сведения о настраиваемых этапов построения и событиях построения см. в разделе [понимание пользовательские шаги построения и события построения](../../ide/understanding-custom-build-steps-and-build-events.md).