---
title: "Проекта PRJ0041 предупреждение сборки | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- PRJ0041
dev_langs:
- C++
helpviewer_keywords:
- PRJ0041
ms.assetid: dc9f4cf9-6bd5-4222-89e8-7802a59bb96b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 231b58cb0c13d1a3f87e010a5100da564b0be806
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="project-build-warning-prj0041"></a>Предупреждение при построении проекта PRJ0041
Не удается найти отсутствующую зависимость «зависимость» для файла «файл». Проект по-прежнему может быть построен, но будет считаться устаревшими, пока этот файл найден.  
  
 Файл (файл ресурсов или.idl/.odl файл, например, содержатся инструкции include, система проектов не удалось разрешить.  
  
 Поскольку система проекта не обрабатывает операторы процессора (например, #if), несоответствующий оператор может оказаться фактически частью сборки.  
  
 Чтобы устранить это предупреждение, удалите все ненужные код в RC-файлов или добавьте файлы заполнитель соответствующего имени.