---
title: Ошибка построения проекта PRJ0024 | Документация Майкрософт
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0024
dev_langs:
- C++
helpviewer_keywords:
- PRJ0024
ms.assetid: 8bde6368-6c1b-4e04-bc5e-3c6d0b8fa1d7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eb539a5f1ee5f1aa5f9d828d93fa6d0dc8690c22
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43215602"
---
# <a name="project-build-error-prj0024"></a>Ошибка построения проекта PRJ0024

> Юникод-путь "*путь*" не может быть преобразована в кодовую страницу ANSI пользователя.

*путь* — исходная версия строки пути Юникода. Эта ошибка может возникать в случаях, где имеется путь в формате Юникод, нельзя напрямую преобразовать в ANSI для текущей кодовой странице системы.

Эта ошибка может возникать, если вы работаете с проектом, который был разработан в системе, используя кодовую страницу, которая не находится на компьютере.

Способ устранения этой ошибки является путь, используйте текст ANSI, или чтобы установить кодовую страницу на компьютер и установите ее в качестве системной настройки по умолчанию.