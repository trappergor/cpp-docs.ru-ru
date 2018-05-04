---
title: Настройка статическую ссылку на код регистратора (C++) | Документы Microsoft
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
ms.openlocfilehash: dca93c8f0fcae578700a9d9970977179fbd142d3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="setting-up-a-static-link-to-the-registrar-code-c-only"></a>Настройка статическую ссылку на код регистратора (C++)
Клиенты C++ можно создать статическую ссылку на коде регистратора. Статическое связывание синтаксического анализа с помощью регистратора добавляет около 5 КБ для сборки выпуска.  
  
 Самый простой способ настроить статическое связывание предполагает указан [DECLARE_REGISTRY_RESOURCEID](reference/registry-macros.md#declare_registry_resourceid) в объявлении объекта. (Это определение по умолчанию, используемого для библиотеки ATL.)  
  
### <a name="to-create-a-static-link-using-declareregistryresourceid"></a>Чтобы создать статические ссылки с использованием DECLARE_REGISTRY_RESOURCEID  
  
1.  Укажите [/D](../build/reference/d-preprocessor-definitions.md) `_ATL_STATIC_REGISTRY` вместо /D **_ATL_DLL**.  
  
2.  Выполните повторную компиляцию.  
  
## <a name="see-also"></a>См. также  
 [Компонент реестра (регистратор)](../atl/atl-registry-component-registrar.md)

