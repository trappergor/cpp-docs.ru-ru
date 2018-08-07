---
title: Метод FtmBase::CreateGlobalInterfaceTable | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::CreateGlobalInterfaceTable
dev_langs:
- C++
helpviewer_keywords:
- CreateGlobalInterfaceTable method
ms.assetid: bb82a0c5-22b9-4844-9204-7922033d8b07
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: de98932420cf5eb0d5b9b13011044e5bfc7b400d
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2018
ms.locfileid: "39569008"
---
# <a name="ftmbasecreateglobalinterfacetable-method"></a>Метод FtmBase::CreateGlobalInterfaceTable
Создает общую таблицу интерфейса (GIT).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
static HRESULT CreateGlobalInterfaceTable(  
   __out IGlobalInterfaceTable **git  
);  
```  
  
### <a name="parameters"></a>Параметры  
 *Git*  
 После завершения этой операции указатель на общую таблицу интерфейса.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе «IGlobalInterfaceTable» в подразделе «COM-интерфейсы» раздела «Ссылки COM» в библиотеке MSDN.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** ftm.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс FtmBase](../windows/ftmbase-class.md)