---
title: Проекта PRJ0041 предупреждение построения | Документация Майкрософт
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
ms.openlocfilehash: 7677c5718783065f64e52f98f7ddbed76e905d2a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46038143"
---
# <a name="project-build-warning-prj0041"></a>Предупреждение при построении проекта PRJ0041

Не удается найти отсутствующую зависимость «зависимость» для файла «файл». Проект по-прежнему может быть построен, но будет считаться устаревшей, пока этот файл найден.

Файл (файл ресурсов или файл.idl/.odl, к примеру, содержатся инструкции include, система проектов не удалось разрешить.

Так как системе проектов не выполняет обработку в операторах препроцессора (например, #if), несоответствующий оператор может оказаться фактически процессе сборки.

Чтобы устранить это предупреждение, удалите все ненужные код в RC-файлов или добавьте файлы заполнителя соответствующего имени.