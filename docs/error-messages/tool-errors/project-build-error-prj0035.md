---
title: "Ошибка построения проекта PRJ0035 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: PRJ0035
dev_langs: C++
helpviewer_keywords: PRJ0035
ms.assetid: 0667116d-338c-40a4-972c-da875f778cb5
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 28d216625f64bab88da76279bb742d02679adfd2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="project-build-error-prj0035"></a>Ошибка построения проекта PRJ0035
XML-файл «файл», содержащий знаки Юникода, не может быть преобразована в кодовую страницу ANSI пользователя.  
  
 ***Содержимое файла в кодировке Юникод***  
  
 ***файл*** XML-файл, создается как командную строку для инструмента веб-развертывания.  
  
 Система проектов обнаружила символы Юникода в некоторых свойствах на странице свойств веб-развертывания, не может быть преобразован неправильно ANSI.  
  
 Способ устранения этой ошибки является обновление содержимое свойства использовать ANSI, а также установите кодовую страницу на компьютере и укажите ее как системный объект по умолчанию.