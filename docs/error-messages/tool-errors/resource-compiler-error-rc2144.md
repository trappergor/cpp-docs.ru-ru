---
title: Ошибка компилятора ресурсов RC2144 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC2144
dev_langs:
- C++
helpviewer_keywords:
- RC2144
ms.assetid: 1b3ff39a-92cd-4a04-b1a3-b1fa6a805813
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 62f9eb2b25919a2336c36a459ef41eece447a490
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46080497"
---
# <a name="resource-compiler-error-rc2144"></a>Ошибка компилятора ресурсов RC2144

PRIMARY LANGUAGE ID не является числом

PRIMARY LANGUAGE ID должен быть шестнадцатеричным идентификатором языка. См. в разделе [языка и строк страны или региона](../../c-runtime-library/locale-names-languages-and-country-region-strings.md) в *Справочник по библиотеке времени выполнения* список допустимых идентификаторов языка.

Эта ошибка также может возникнуть, если с помощью какого-либо средства ресурсы были добавлены в RC-файл или удалены из RC-файла. Чтобы устранить эту проблему, откройте RC-файл в текстовом редакторе и вручную удалите все неиспользуемые ресурсы.