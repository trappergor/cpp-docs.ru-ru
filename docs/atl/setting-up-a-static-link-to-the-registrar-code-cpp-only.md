---
title: Настройка статической ссылки на код регистратора (только C++)
description: Как статически связать код C++ с кодом регистратора ATL.
ms.date: 09/03/2020
helpviewer_keywords:
- statically linking to ATL Registrar code
- linking [C++], to ATL Registrar code
ms.assetid: 835f5885-87a6-48fa-91e6-60988ee65538
ms.openlocfilehash: f08f7d9433ae1344c7a98a5c52502d03bad21e91
ms.sourcegitcommit: 0df2b7ab4e81284c5248e4584767591dcc1950c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2020
ms.locfileid: "89609162"
---
# <a name="setting-up-a-static-link-to-the-registrar-code-c-only"></a>Настройка статической ссылки на код регистратора (только C++)

Клиенты C++ могут создать статическую ссылку на код регистратора. Статическая компоновка средства синтаксического анализа регистратора добавляет примерно 5 КБ в сборку выпуска.

Самый простой способ настроить статическую компоновку предполагает, что вы указали [`DECLARE_REGISTRY_RESOURCEID`](reference/registry-macros.md#declare_registry_resourceid) в объявлении объекта. (Это спецификация по умолчанию, используемая библиотекой ATL.)

## <a name="to-create-a-static-link-using-declare_registry_resourceid"></a>Создание статической связи с помощью `DECLARE_REGISTRY_RESOURCEID`

1. Укажите **`/D _ATL_STATIC_REGISTRY`** вместо **`/D _ATL_DLL`** в командной строке CL. Дополнительные сведения см. на веб-сайте [`/D`](../build/reference/d-preprocessor-definitions.md).

1. RECOMPILE.

## <a name="see-also"></a>См. также раздел

[Компонент реестра (регистратор)](../atl/atl-registry-component-registrar.md)
