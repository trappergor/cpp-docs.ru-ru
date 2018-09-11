---
title: Ошибка построения проекта PRJ0035 | Документация Майкрософт
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0035
dev_langs:
- C++
helpviewer_keywords:
- PRJ0035
ms.assetid: 0667116d-338c-40a4-972c-da875f778cb5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dd36604763e28fc3f228adec27d0c3775a327d66
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43213029"
---
# <a name="project-build-error-prj0035"></a>Ошибка построения проекта PRJ0035

> XML-файл "*файл*", содержащий знаки Юникода, не может быть преобразована в кодовую страницу ANSI пользователя.
>
> *Содержимое файла в кодировке Юникод*

*файл* является файлом XML, созданным как командную строку для инструмента веб-развертывания.

Система проектов обнаружила символов Юникода в некоторые свойства на странице свойств веб-развертывания, не может быть правильно преобразован ANSI.

Способ устранения этой ошибки является обновление содержимое свойства использовать ANSI, а также установите кодовую страницу на компьютере и установите ее в качестве системной настройки по умолчанию.