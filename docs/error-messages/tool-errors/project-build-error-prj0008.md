---
title: Ошибка построения проекта PRJ0008
ms.date: 11/04/2016
f1_keywords:
- PRJ0008
helpviewer_keywords:
- PRJ0008
ms.assetid: 6bf7f17a-d2a8-4826-99c7-d600d846952f
ms.openlocfilehash: 7d1c11ab7539f25d371c0bfbd2853b6155c9661c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80192962"
---
# <a name="project-build-error-prj0008"></a>Ошибка построения проекта PRJ0008

Не удалось удалить файл "файл".

**Убедитесь, что файл не открыт другим процессом и не защищен от записи.**

Во время перестроения или очистки визуальный C++ элемент удаляет все известные промежуточные и выходные файлы для сборки, а также все файлы, которые соответствуют спецификации шаблона в свойстве " **расширения для удаления** " на [странице свойств Общие параметры конфигурации](../../build/reference/general-property-page-project.md).

Эта ошибка возникает, если визуальный C++ элемент не может удалить файл. Чтобы устранить эту ошибку, сделайте файл и его каталог записываемым для пользователя, выполняющего сборку.
