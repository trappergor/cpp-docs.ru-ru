---
title: Предупреждение средств компоновщика LNK4086
ms.date: 11/04/2016
f1_keywords:
- LNK4086
helpviewer_keywords:
- LNK4086
ms.assetid: ea1eecbb-ba2c-41bb-9a4f-fa0808a4b92d
ms.openlocfilehash: f692f848825cd3d8e5e1fc042cb94d7cce8ea6bf
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87195815"
---
# <a name="linker-tools-warning-lnk4086"></a>Предупреждение средств компоновщика LNK4086

точка входа "функция" не __stdcall с числом байтов аргументов; образ не может быть запущен

Точка входа для библиотеки DLL должна иметь значение **`__stdcall`** . Либо перекомпилируйте функцию с параметром [/gz](../../build/reference/gd-gr-gv-gz-calling-convention.md) , либо укажите **`__stdcall`** или WINAPI при определении функции.
