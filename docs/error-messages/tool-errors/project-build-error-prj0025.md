---
title: Ошибка построения проекта PRJ0025 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0025
dev_langs:
- C++
helpviewer_keywords:
- PRJ0025
ms.assetid: 57725c78-bc63-44f3-9667-2969b2d7c41d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 087a5d5af8ed92bdd0446ae87af037acbfd38a95
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33316989"
---
# <a name="project-build-error-prj0025"></a>Ошибка построения проекта PRJ0025
Пакетный файл «файл», содержащий знаки Юникода, не может быть преобразована в кодовую страницу ANSI пользователя.  
  
 ***Содержимое файла в кодировке Юникод***  
  
 Система проектов найти содержимое в кодировке Юникод в пользовательское правило сборки или сборки события, которое не может правильно преобразован в текущую кодовую страницу ANSI пользователя.  
  
 Способ устранения этой ошибки является обновления содержимого правила построения или события использовать ANSI, а также установите кодовую страницу на компьютере и установить его по умолчанию системы сборки.  
  
 Дополнительные сведения о настраиваемых этапов построения и событиях построения см. в разделе [понимание пользовательские шаги построения и события построения](../../ide/understanding-custom-build-steps-and-build-events.md).