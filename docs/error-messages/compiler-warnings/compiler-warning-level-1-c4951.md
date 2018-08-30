---
title: Предупреждение компилятора (уровень 1) C4951 | Документация Майкрософт
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4951
dev_langs:
- C++
helpviewer_keywords:
- C4951
ms.assetid: 669d8bb7-5efa-4ba9-99db-4e65addbf054
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e26c4bc176a54f063a3f9bce2faf451a9c0406f0
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43204239"
---
# <a name="compiler-warning-level-1-c4951"></a>Предупреждение компилятора (уровень 1) C4951

> "*функция*" была изменена после сбора данных профилирования данные профиля функции не используются

Функция была изменена во входном модуле при компоновке с параметром [/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md), поэтому данные профиля сейчас недопустимы. Входной модуль был повторно скомпилирован после **/LTCG: PGINSTRUMENT** и содержит функцию (*функция*) с другим потоком управления по сравнению был в модуле во время  **/LTCG: PGINSTRUMENT** операции.

Это предупреждение носит информационный характер. Чтобы устранить его, выполните компоновку с параметром **/LTCG:PGINSTRUMENT**, повторите все тестовые запуски и выполните компоновку с параметром **/LTCG:PGOPTIMIZE**.

Вместо этого предупреждения будет ошибка, если использовался параметр **/LTCG:PGOPTIMIZE** .