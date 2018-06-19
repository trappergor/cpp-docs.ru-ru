---
title: Создание вычисляемого объекта | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- aggregation [C++], creating aggregated objects
- aggregate objects [C++], creating
ms.assetid: fc29d7aa-fd53-4276-9c2f-37379f71b179
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 35ddbd6b8db853967a70de0427cc842689d55c82
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32355024"
---
# <a name="creating-an-aggregated-object"></a>Создание вычисляемого объекта
Делегаты статистической обработки **IUnknown** вызовов, предоставляя указатель на внешний объект **IUnknown** к внутреннему объекту.  
  
### <a name="to-create-an-aggregated-object"></a>Для создания вычисляемого объекта  
  
1.  Добавить **IUnknown** указатель к классу и инициализируйте его, чтобы **NULL** в конструкторе.  
  
2.  Переопределить [FinalConstruct](../atl/reference/ccomobjectrootex-class.md#finalconstruct) для создания агрегата.  
  
3.  Используйте **IUnknown** указателя, определенных на шаге 1, в качестве второго параметра для [COM_INTERFACE_ENTRY_AGGREGATE](reference/com-interface-entry-macros.md#com_interface_entry_aggregate) макросы.  
  
4.  Переопределить [FinalRelease](../atl/reference/ccomobjectrootex-class.md#finalrelease) для освобождения **IUnknown** указателя.  
  
> [!NOTE]
>  Использовать и интерфейс из агрегированных объекта во время выпуска `FinalConstruct`, следует добавить [DECLARE_PROTECT_FINAL_CONSTRUCT](reference/aggregation-and-class-factory-macros.md#declare_protect_final_construct) макроса в определении класса объекта.  
  
## <a name="see-also"></a>См. также  
 [Основы COM-объектов ATL](../atl/fundamentals-of-atl-com-objects.md)

