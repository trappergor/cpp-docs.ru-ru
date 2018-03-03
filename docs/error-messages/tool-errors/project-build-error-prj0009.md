---
title: "Ошибка построения проекта PRJ0009 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- PRJ0009
dev_langs:
- C++
helpviewer_keywords:
- PRJ0009
ms.assetid: 89291778-cda4-495d-983f-ddcc06dfc98b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0ee183c24cf330b54a335efbd0bbe2b00e18d209
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="project-build-error-prj0009"></a>Ошибка построения проекта PRJ0009
Построение журнала не может быть открыт для записи.  
  
 **Убедитесь, что файл не открыт другим процессом и не защищен от записи.**  
  
 После установки параметра **ведение журнала построения** свойства **Да** и выполняет построение или перестроение, Visual C++ не удалось открыть журнал сборки в монопольном режиме.  
  
 Проверить **ведение журнала построения** установки, открыв **параметры** диалоговое окно (на **средства** меню, нажмите кнопку **параметры** команда) и затем При выборе **Построение VC ++** в **проекты** папки. Файл сборки называется BuildLog.htm и записывается в промежуточный каталог $(IntDir).  
  
 Возможные причины этой ошибки:  
  
-   Запускается два процесса Visual C++ и попытке выполнить сборку одинаковую конфигурацию одного проекта в обоих одновременно.  
  
-   В процессе, который блокирует файл открывается файл журнала сборки.  
  
-   Пользователь не имеет разрешения на создание файла.  
  
-   Текущий пользователь имеет доступ на запись в файл BuildLog.htm.