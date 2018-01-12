---
title: "Настройка статическую ссылку на код регистратора (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- statically linking to ATL Registrar code
- linking [C++], to ATL Registrar code
ms.assetid: 835f5885-87a6-48fa-91e6-60988ee65538
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d49ed2a56738ec784c8a1a2cc3c13239f7317270
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="setting-up-a-static-link-to-the-registrar-code-c-only"></a>Настройка статическую ссылку на код регистратора (C++)
Клиенты C++ можно создать статическую ссылку на коде регистратора. Статическое связывание синтаксического анализа с помощью регистратора добавляет около 5 КБ для сборки выпуска.  
  
 Самый простой способ настроить статическое связывание предполагает указан [DECLARE_REGISTRY_RESOURCEID](reference/registry-macros.md#declare_registry_resourceid) в объявлении объекта. (Это определение по умолчанию, используемого для библиотеки ATL.)  
  
### <a name="to-create-a-static-link-using-declareregistryresourceid"></a>Чтобы создать статические ссылки с использованием DECLARE_REGISTRY_RESOURCEID  
  
1.  Укажите [/D](../build/reference/d-preprocessor-definitions.md) `_ATL_STATIC_REGISTRY` вместо /D**_ATL_DLL**.  
  
2.  Выполните повторную компиляцию.  
  
## <a name="see-also"></a>См. также  
 [Компонент реестра (регистратор)](../atl/atl-registry-component-registrar.md)

