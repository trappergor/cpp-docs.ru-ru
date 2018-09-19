---
title: Ошибка построения проекта PRJ0027 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0027
dev_langs:
- C++
helpviewer_keywords:
- PRJ0027
ms.assetid: 85d73a78-4b9e-4553-9f5d-2d76c48a790a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c642c678c7db29b9826449731f07ad90bc865294
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46062063"
---
# <a name="project-build-error-prj0027"></a>Ошибка построения проекта PRJ0027

Сообщение журнала Юникода, что «содержимое» содержит содержимое, которое не может быть преобразована в кодовую страницу ANSI пользователя.

Обычно только появится это предупреждение в сочетании с ошибками при создании пакета или файла ответов.

Способ устранения этой ошибки является обновление содержимое журнала построения для использования ANSI или установите кодовую страницу на компьютере и установите ее в качестве системной настройки по умолчанию.