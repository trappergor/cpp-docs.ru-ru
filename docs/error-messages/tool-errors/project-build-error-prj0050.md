---
title: Ошибка построения проекта PRJ0050 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0050
dev_langs:
- C++
helpviewer_keywords:
- PRJ0050
ms.assetid: ceef3b37-0acf-4abd-ac62-aa830b4fa145
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bb3949ea0db2f1667aecf1aeeefd922b192cbf41
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46100595"
---
# <a name="project-build-error-prj0050"></a>Ошибка построения проекта PRJ0050

Не удалось зарегистрировать выход. Убедитесь, что у вас есть соответствующие разрешения на изменение реестра.

Система сборки Visual C++ не удалось зарегистрировать выходные данные сборки (dll или .exe). Необходимо войти в систему как администратор, вносить изменения в реестр.

При создании DLL-библиотеку, можно попытаться зарегистрировать библиотеку DLL, вручную с помощью regsvr32.exe, это будет выведена информация о причинах сбоя.

Если вы не создаете DLL-файл, просмотрите журнал построения для команды, которая вызывает ошибку.