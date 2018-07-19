---
title: Ошибка построения проекта PRJ0035 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0035
dev_langs:
- C++
helpviewer_keywords:
- PRJ0035
ms.assetid: 0667116d-338c-40a4-972c-da875f778cb5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 52d4726cd6fc8091225532b2cfda33c6115c673a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33321864"
---
# <a name="project-build-error-prj0035"></a>Ошибка построения проекта PRJ0035
XML-файл «файл», содержащий знаки Юникода, не может быть преобразована в кодовую страницу ANSI пользователя.  
  
 ***Содержимое файла в кодировке Юникод***  
  
 ***файл*** XML-файл, создается как командную строку для инструмента веб-развертывания.  
  
 Система проектов обнаружила символы Юникода в некоторых свойствах на странице свойств веб-развертывания, не может быть преобразован неправильно ANSI.  
  
 Способ устранения этой ошибки является обновление содержимое свойства использовать ANSI, а также установите кодовую страницу на компьютере и укажите ее как системный объект по умолчанию.