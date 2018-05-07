---
title: Ошибка построения проекта PRJ0002 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0002
dev_langs:
- C++
helpviewer_keywords:
- PRJ0002
ms.assetid: 1c820b1f-9a24-4681-80ed-4fcbfd7caa00
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 54e1870ce9137ba172f848a499dd31133119eea0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="project-build-error-prj0002"></a>Ошибка построения проекта PRJ0002
результат ошибки, возвращенные «Командная строка».  
  
 Командная ***командной строки***, которой была создана из пользовательского ввода в **страницы свойств** диалоговое окно, возвращается код ошибки, но не сведения будут отображаться в окне вывода.  
  
 Разрешение для этой ошибки зависит от того, какой инструмент создает ошибку. MIDL вы получите представление о том, что пошло не так, если определено /o (перенаправление вывода).  
  
 Причина этой ошибки может быть также пакетного файла, например этапа настраиваемого построения или события построения, который не показывающего сведения о сбоях.