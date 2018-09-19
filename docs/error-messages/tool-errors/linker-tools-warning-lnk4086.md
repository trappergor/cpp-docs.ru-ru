---
title: Предупреждение средств компоновщика LNK4086 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4086
dev_langs:
- C++
helpviewer_keywords:
- LNK4086
ms.assetid: ea1eecbb-ba2c-41bb-9a4f-fa0808a4b92d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 21a2ee7660f0ad78d04f7edb191929296c8d47a9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46079236"
---
# <a name="linker-tools-warning-lnk4086"></a>Предупреждение средств компоновщика LNK4086

EntryPoint «функция» не является __stdcall с 'number' байт аргументов; образ нельзя запустить

Точка входа для библиотеки DLL должна быть `__stdcall`. Либо перекомпилировать функции с [/Gz](../../build/reference/gd-gr-gv-gz-calling-convention.md) параметр или указать `__stdcall` или WINAPI при определении функции.