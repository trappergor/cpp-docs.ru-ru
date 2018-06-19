---
title: Проекта PRJ0041 предупреждение сборки | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0041
dev_langs:
- C++
helpviewer_keywords:
- PRJ0041
ms.assetid: dc9f4cf9-6bd5-4222-89e8-7802a59bb96b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6e845967b0a7116d6edade98b571de5bc1bcd9a1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33318065"
---
# <a name="project-build-warning-prj0041"></a>Предупреждение при построении проекта PRJ0041
Не удается найти отсутствующую зависимость «зависимость» для файла «файл». Проект по-прежнему может быть построен, но будет считаться устаревшими, пока этот файл найден.  
  
 Файл (файл ресурсов или.idl/.odl файл, например, содержатся инструкции include, система проектов не удалось разрешить.  
  
 Поскольку система проекта не обрабатывает операторы процессора (например, #if), несоответствующий оператор может оказаться фактически частью сборки.  
  
 Чтобы устранить это предупреждение, удалите все ненужные код в RC-файлов или добавьте файлы заполнитель соответствующего имени.