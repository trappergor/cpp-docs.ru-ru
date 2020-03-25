---
title: Ошибка средств компоновщика LNK1302
ms.date: 11/04/2016
f1_keywords:
- LNK1302
helpviewer_keywords:
- LNK1302
ms.assetid: aea3c753-c2c4-4249-bbc3-f2d4f0164b5e
ms.openlocfilehash: 8323fa234851ce3ba12083adb74d5ee0fba0ac69
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194932"
---
# <a name="linker-tools-error-lnk1302"></a>Ошибка средств компоновщика LNK1302

поддерживаются только ссылки на надежные. netmodule. не удается связать файл. netmodule

NETMODULE-код (скомпилированный с параметром **/LN**) был передан компоновщику при попытке вызвать компоновку MSIL.  C++ Модуль является допустимым для компоновки MSIL, если он компилируется с **/clr: Сейф**.

Чтобы исправить эту ошибку, Скомпилируйте с **параметром/clr: Сейф** , чтобы включить компоновку MSIL, или передайте компоновщику вместо модуля файл **/CLR** или **/clr: pure** . obj.

Дополнительные сведения см. в разделе

- [/LN (создание модуля MSIL)](../../build/reference/ln-create-msil-module.md)

- [NETMODULE-файлы в качестве входных файлов компоновщика](../../build/reference/netmodule-files-as-linker-input.md)
