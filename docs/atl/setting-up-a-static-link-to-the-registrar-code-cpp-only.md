---
title: Настройка статической ссылки на код регистратора (только C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- statically linking to ATL Registrar code
- linking [C++], to ATL Registrar code
ms.assetid: 835f5885-87a6-48fa-91e6-60988ee65538
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7a66ca33aa95ea6ffd59860cf0a55e51266ef5cb
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43757702"
---
# <a name="setting-up-a-static-link-to-the-registrar-code-c-only"></a>Настройка статической ссылки на код регистратора (только C++)

Клиенты C++ можно создавать статической ссылки в коде регистратора. Статическое связывание средства синтаксического анализа регистратора добавляет около 5 КБ построения выпуска.

Самый простой способ настроить статическое связывание предполагается, что вы указали [DECLARE_REGISTRY_RESOURCEID](reference/registry-macros.md#declare_registry_resourceid) в объявлении объекта. (Это спецификация по умолчанию, используемых для библиотеки ATL.)

### <a name="to-create-a-static-link-using-declareregistryresourceid"></a>Чтобы создать статическую ссылку с помощью DECLARE_REGISTRY_RESOURCEID

1. Укажите [/D](../build/reference/d-preprocessor-definitions.md) `_ATL_STATIC_REGISTRY` вместо /D **_ATL_DLL**.

2. Выполните повторную компиляцию.

## <a name="see-also"></a>См. также

[Компонент реестра (регистратор)](../atl/atl-registry-component-registrar.md)

