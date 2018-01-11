---
title: "CRowset::Insert | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CRowset<TAccessor>.Insert
- CRowset.Insert
- CRowset<TAccessor>.Insert
- CRowset<TAccessor>::Insert
- ATL::CRowset<TAccessor>::Insert
- ATL.CRowset.Insert
- CRowset::Insert
- ATL::CRowset::Insert
dev_langs: C++
helpviewer_keywords: Insert method
ms.assetid: 6a64a1c3-10ac-4296-8685-0fd6fe63a13b
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 75dfe26fa04f8e639b3d391a9dc703a9a98c70c4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="crowsetinsert"></a>CRowset::Insert
Создает и инициализирует новую строку, используя данные из метода доступа.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      HRESULT Insert(   
   int nAccessor = 0,   
   bool bGetHRow = false    
) throw( );  
```  
  
#### <a name="parameters"></a>Параметры  
 `nAccessor`  
 [in] Число методов доступа, используемый для вставки данных.  
  
 *bGetHRow*  
 [in] Указывает, получаются ли дескриптор для вставляемой строки.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`.  
  
## <a name="remarks"></a>Примечания  
 Этот метод требует дополнительный интерфейс `IRowsetChange`, который может поддерживается не всеми поставщиками; Если это так, метод возвращает **E_NOINTERFACE**. Необходимо также задать **DBPROP_IRowsetChange** для `VARIANT_TRUE` перед вызовом **откройте** для таблицы или команду, содержащую набор строк.  
  
 Вставка может завершиться ошибкой, если один или несколько столбцов не может быть перезаписан. Измените схему курсоров, чтобы исправить это.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как для доступа к источнику данных через набор строк, а затем вставить строку с помощью таблицы в этом наборе строк.  
  
 Во-первых создайте класс таблицы путем вставки нового объекта ATL в проект. Например, щелкните правой кнопкой мыши проект в рабочей области и выберите **новый объект ATL**. Из **доступа к данным** категории, выберите **потребителя**. Создание пользовательского объекта типа **таблицы**. (При выборе **таблицы** создает набор строк непосредственно из таблицы; при выборе **команда** создает набор строк с помощью команды SQL.) Выберите источник данных, указания таблицы, по которому необходимо получить доступ к этому источнику данных. При вызове объекта получателя **CCustomerTable**, затем будет реализован вставки кода следующим образом:  
  
 [!code-cpp[NVC_OLEDB_Consumer#10](../../data/oledb/codesnippet/cpp/crowset-insert_1.cpp)]  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CRowset](../../data/oledb/crowset-class.md)