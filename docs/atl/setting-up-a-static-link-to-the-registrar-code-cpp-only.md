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
ms.openlocfilehash: 3bde1d369ce5339f07ea36979ef50ddccb0d30d1
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/08/2018
ms.locfileid: "48860281"
---
# <a name="setting-up-a-static-link-to-the-registrar-code-c-only"></a>Настройка статической ссылки на код регистратора (только C++)

Клиенты C++ можно создавать статической ссылки в коде регистратора. Статическое связывание средства синтаксического анализа регистратора добавляет около 5 КБ построения выпуска.

Самый простой способ настроить статическое связывание предполагается, что вы указали [DECLARE_REGISTRY_RESOURCEID](reference/registry-macros.md#declare_registry_resourceid) в объявлении объекта. (Это спецификация по умолчанию, используемых для библиотеки ATL.)

## <a name="to-create-a-static-link-using-declareregistryresourceid"></a>Чтобы создать статическую ссылку с помощью DECLARE_REGISTRY_RESOURCEID

1. Укажите [/D](../build/reference/d-preprocessor-definitions.md) `_ATL_STATIC_REGISTRY` вместо /D **_ATL_DLL**.

1. Выполните повторную компиляцию.

## <a name="see-also"></a>См. также

[Компонент реестра (регистратор)](../atl/atl-registry-component-registrar.md)
