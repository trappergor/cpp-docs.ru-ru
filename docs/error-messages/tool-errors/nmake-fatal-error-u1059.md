---
title: Неустранимая ошибка NMAKE U1059 | Документация Майкрософт
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1059
dev_langs:
- C++
helpviewer_keywords:
- U1059
ms.assetid: b21d9198-9c63-40d0-b589-80e17294ce24
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8b54919398c757bfe05f747ff57341f31decfc61
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43200794"
---
# <a name="nmake-fatal-error-u1059"></a>Неустранимая ошибка NMAKE U1059

> Синтаксическая ошибка: "}" отсутствует в зависимости

Неправильно указан путь поиска для зависимости. Существовали пробелы в пути или закрывающей фигурной скобкой (**}**) была пропущена.

Синтаксис для спецификацию каталогов для зависимости:

> **{** *каталоги* **} зависимые**

где *каталоги* указывает один или несколько путей, разделяя их точкой с запятой (**;**). Пробелы не допускаются.

Если макрос заменяется всех или части пути поиска, убедитесь, что существует без пробелов в расширении макроса.