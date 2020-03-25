---
title: Предупреждение средств компоновщика LNK4086
ms.date: 11/04/2016
f1_keywords:
- LNK4086
helpviewer_keywords:
- LNK4086
ms.assetid: ea1eecbb-ba2c-41bb-9a4f-fa0808a4b92d
ms.openlocfilehash: 6e012ceb5e20855353c69bbcde85fb78afad2011
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80183427"
---
# <a name="linker-tools-warning-lnk4086"></a>Предупреждение средств компоновщика LNK4086

точка входа "функция" не __stdcall с числом байтов аргументов; образ не может быть запущен

Точка входа для библиотеки DLL должна быть `__stdcall`. Либо перекомпилируйте функцию с параметром [/gz](../../build/reference/gd-gr-gv-gz-calling-convention.md) , либо укажите `__stdcall` или WINAPI при определении функции.
