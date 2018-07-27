---
title: Класс RoInitializeWrapper | Документы Microsoft
ms.custom: ''
ms.date: 05/20/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper
dev_langs:
- C++
ms.assetid: 4055fbe0-63a7-4c06-b5a0-414fda5640e5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cac71857e6b472f11d1c9eaba48d181ea78fb456
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34705596"
---
# <a name="roinitializewrapper-class"></a>Класс RoInitializeWrapper
Инициализирует среду выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class RoInitializeWrapper  
```  
  
## <a name="remarks"></a>Примечания  
 RoInitializeWrapper — удобный метод, который инициализирует среду выполнения Windows и возвращает значение HRESULT, указывающее, успешно ли выполнена операция. Так как вызывает деструктор класса `::Windows::Foundation::Uninitialize`, экземпляры `RoInitializeWrapper` должны объявляться на верхнего уровня и в глобальной области.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Конструктор RoInitializeWrapper::RoInitializeWrapper](../windows/roinitializewrapper-roinitializewrapper-constructor.md)|Инициализирует новый экземпляр класса RoInitializeWrapper.|  
|[Деструктор RoInitializeWrapper::~RoInitializeWrapper](../windows/roinitializewrapper-tilde-roinitializewrapper-destructor.md)|Удаляет текущий экземпляр класса RoInitializeWrapper.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Оператор RoInitializeWrapper::HRESULT()](../windows/roinitializewrapper-hresult-parens-operator.md)|Возвращает значение HRESULT, полученное конструктором RoInitializeWrapper.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `RoInitializeWrapper`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Wrappers](../windows/microsoft-wrl-wrappers-namespace.md)