---
title: Ошибка профильной оптимизации PG0165
description: Описание ошибок PG0165 при чтении данных профильной оптимизации (PGO).
ms.date: 10/30/2019
f1_keywords:
- PG0165
helpviewer_keywords:
- PG0165
ms.assetid: e98122e7-ddee-4a2c-96b2-d232e4c65f3e
ms.openlocfilehash: c5e5c5d37f8c70a6c2a3d9f7a43c13bb46d0e25a
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626801"
---
# <a name="profile-guided-optimization-error-pg0165"></a>Ошибка профильной оптимизации PG0165

Произошла ошибка при чтении данных профильной оптимизации. Эта ошибка может появиться в нескольких формах:

> Чтение*файла "filename. PGD*": "версия PGD не поддерживается (несовпадение версий)".

Файлы PGD относятся к конкретному набору инструментов компилятора. Эта ошибка возникает при использовании другого компилятора, отличного от того, который использовался для создания *файла filename. PGD*. Ошибка указывает, что этот набор инструментов компилятора не может использовать данные из *файла filename. PGD* для оптимизации текущей программы. Чтобы устранить эту проблему, повторно создайте *файл filename*. PGD с помощью текущего набора инструментов компилятора.

> Чтение файла "*filename. PGD*": "PGD-файл доступен только для чтения".

Эта ошибка отображается, если PGD-файл помечен в файловой системе как "только для чтения". Чтобы устранить эту проблему, измените атрибуты файла на чтение и запись.
