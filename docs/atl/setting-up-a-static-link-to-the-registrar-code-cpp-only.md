---
title: Настройка статической ссылки на код регистратора (только C++)
ms.date: 11/04/2016
helpviewer_keywords:
- statically linking to ATL Registrar code
- linking [C++], to ATL Registrar code
ms.assetid: 835f5885-87a6-48fa-91e6-60988ee65538
ms.openlocfilehash: 11600b47abbbd247d099d871fce5e9d5d17d3cf4
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2018
ms.locfileid: "51327893"
---
# <a name="setting-up-a-static-link-to-the-registrar-code-c-only"></a>Настройка статической ссылки на код регистратора (только C++)

Клиенты C++ можно создавать статической ссылки в коде регистратора. Статическое связывание средства синтаксического анализа регистратора добавляет около 5 КБ построения выпуска.

Самый простой способ настроить статическое связывание предполагается, что вы указали [DECLARE_REGISTRY_RESOURCEID](reference/registry-macros.md#declare_registry_resourceid) в объявлении объекта. (Это спецификация по умолчанию, используемых для библиотеки ATL.)

## <a name="to-create-a-static-link-using-declareregistryresourceid"></a>Чтобы создать статическую ссылку с помощью DECLARE_REGISTRY_RESOURCEID

1. Укажите [/D](../build/reference/d-preprocessor-definitions.md)  **\_ATL\_СТАТИЧЕСКИЙ\_РЕЕСТРА** вместо **/D \_ATL\_DLL**.

1. Выполните повторную компиляцию.

## <a name="see-also"></a>См. также

[Компонент реестра (регистратор)](../atl/atl-registry-component-registrar.md)
