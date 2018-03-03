---
title: "Ошибка построения проекта PRJ0002 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- PRJ0002
dev_langs:
- C++
helpviewer_keywords:
- PRJ0002
ms.assetid: 1c820b1f-9a24-4681-80ed-4fcbfd7caa00
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 81d7f45fb2145d0f47716841a50c9320fd46833c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="project-build-error-prj0002"></a>Ошибка построения проекта PRJ0002
результат ошибки, возвращенные «Командная строка».  
  
 Командная ***командной строки***, которой была создана из пользовательского ввода в **страницы свойств** диалоговое окно, возвращается код ошибки, но не сведения будут отображаться в окне вывода.  
  
 Разрешение для этой ошибки зависит от того, какой инструмент создает ошибку. MIDL вы получите представление о том, что пошло не так, если определено /o (перенаправление вывода).  
  
 Причина этой ошибки может быть также пакетного файла, например этапа настраиваемого построения или события построения, который не показывающего сведения о сбоях.