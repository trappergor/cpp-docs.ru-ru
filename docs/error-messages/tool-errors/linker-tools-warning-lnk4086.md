---
title: Предупреждение средств компоновщика LNK4086
ms.date: 11/04/2016
f1_keywords:
- LNK4086
helpviewer_keywords:
- LNK4086
ms.assetid: ea1eecbb-ba2c-41bb-9a4f-fa0808a4b92d
ms.openlocfilehash: c6a5a0714e070e6cf3aee8efcdfbdfa07fa9ee69
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50427863"
---
# <a name="linker-tools-warning-lnk4086"></a>Предупреждение средств компоновщика LNK4086

EntryPoint «функция» не является __stdcall с 'number' байт аргументов; образ нельзя запустить

Точка входа для библиотеки DLL должна быть `__stdcall`. Либо перекомпилировать функции с [/Gz](../../build/reference/gd-gr-gv-gz-calling-convention.md) параметр или указать `__stdcall` или WINAPI при определении функции.