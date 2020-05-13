---
title: Ошибка компилятора ресурсов RC2144
ms.date: 11/04/2016
f1_keywords:
- RC2144
helpviewer_keywords:
- RC2144
ms.assetid: 1b3ff39a-92cd-4a04-b1a3-b1fa6a805813
ms.openlocfilehash: 1b080916642fc1be4b22820668c4cb4137675425
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80191201"
---
# <a name="resource-compiler-error-rc2144"></a>Ошибка компилятора ресурсов RC2144

PRIMARY LANGUAGE ID не является числом

PRIMARY LANGUAGE ID должен быть шестнадцатеричным идентификатором языка. Допустимые идентификаторы языков см. в разделе [Языки и настройки для стран и регионов](../../c-runtime-library/locale-names-languages-and-country-region-strings.md) в *справочнике по библиотеке среды выполнения* .

Эта ошибка также может возникнуть, если с помощью какого-либо средства ресурсы были добавлены в RC-файл или удалены из RC-файла. Чтобы устранить эту проблему, откройте RC-файл в текстовом редакторе и вручную удалите все неиспользуемые ресурсы.
