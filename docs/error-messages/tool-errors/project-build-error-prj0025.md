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
ms.openlocfilehash: 263c5df7e2f34fdaa5131a65f8820080875b569d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="project-build-error-prj0025"></a>Ошибка построения проекта PRJ0025
Пакетный файл «файл», содержащий знаки Юникода, не может быть преобразована в кодовую страницу ANSI пользователя.  
  
 ***Содержимое файла в кодировке Юникод***  
  
 Система проектов найти содержимое в кодировке Юникод в пользовательское правило сборки или сборки события, которое не может правильно преобразован в текущую кодовую страницу ANSI пользователя.  
  
 Способ устранения этой ошибки является обновления содержимого правила построения или события использовать ANSI, а также установите кодовую страницу на компьютере и установить его по умолчанию системы сборки.  
  
 Дополнительные сведения о настраиваемых этапов построения и событиях построения см. в разделе [понимание пользовательские шаги построения и события построения](../../ide/understanding-custom-build-steps-and-build-events.md).