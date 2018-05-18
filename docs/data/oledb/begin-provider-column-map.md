---
title: BEGIN_PROVIDER_COLUMN_MAP | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- BEGIN_PROVIDER_COLUMN_MAP
dev_langs:
- C++
helpviewer_keywords:
- BEGIN_PROVIDER_COLUMN_MAP macro
ms.assetid: 506b8c0f-6be9-4c97-ba81-c4b7f7d428fa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: eff2aa003f81ed3fcf5ba9152bc17002be0a4db2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="beginprovidercolumnmap"></a>BEGIN_PROVIDER_COLUMN_MAP
Отмечает начало карты записей столбцов поставщика.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
BEGIN_PROVIDER_COLUMN_MAP(theClass)  
  
```  
  
#### <a name="parameters"></a>Параметры  
 `theClass`  
 [in] Имя класса, к которому принадлежит эта карта.  
  
## <a name="example"></a>Пример  
 Ниже приведен образец поставщика сопоставление столбцов.  
  
 [!code-cpp[NVC_OLEDB_Provider#4](../../data/oledb/codesnippet/cpp/begin-provider-column-map_1.h)]  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Макросы для шаблонов поставщика OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Создание поставщика OLE DB](../../data/oledb/creating-an-ole-db-provider.md)