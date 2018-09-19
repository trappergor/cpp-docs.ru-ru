---
title: Ошибка построения проекта PRJ0008 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0008
dev_langs:
- C++
helpviewer_keywords:
- PRJ0008
ms.assetid: 6bf7f17a-d2a8-4826-99c7-d600d846952f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d7c24634a845423de590228af01cb9f4779e37ab
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46062791"
---
# <a name="project-build-error-prj0008"></a>Ошибка построения проекта PRJ0008

Не удалось удалить файл «файл».

**Убедитесь, что файл не открыт другим процессом и не защищен от записи.**

Во время перестроения или очистки Visual C++ удаляет все известные промежуточных и выходных файлов для сборки, а также все файлы, которые удовлетворяют требованиям подстановочный знак в **расширения нужно удалять при очистке** свойство в [Общие Страница свойств параметров конфигурации](../../ide/general-property-page-project.md).

Вы увидите эту ошибку, если Visual C++ не удается удалить файл. Чтобы устранить эту ошибку, сделать файл и каталог доступным для записи для пользователя, выполняющего сборки.