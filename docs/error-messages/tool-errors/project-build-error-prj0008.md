---
title: "Ошибка построения проекта PRJ0008 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: PRJ0008
dev_langs: C++
helpviewer_keywords: PRJ0008
ms.assetid: 6bf7f17a-d2a8-4826-99c7-d600d846952f
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1740b0cf1edfc90258de4fe26478298ddf2875c6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="project-build-error-prj0008"></a>Ошибка построения проекта PRJ0008
Не удалось удалить файл «файл».  
  
 **Убедитесь, что файл не открыт другим процессом и не защищен от записи.**  
  
 Во время перестроения или очистки Visual C++ удаляет все известные промежуточных и выходных файлов для сборки, а также все файлы, которые удовлетворяют требованиям подстановочный знак в **расширения для удаления при очистке** свойства [Общие Страница свойств параметров конфигурации](../../ide/general-property-page-project.md).  
  
 Эта ошибка возникает, если Visual C++ не удается удалить файл. Чтобы устранить эту ошибку, убедитесь в файл и каталог для записи для пользователя, выполняющего сборки.