---
title: Класс IAccessorImpl | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IAccessorImpl
dev_langs:
- C++
helpviewer_keywords:
- IAccessorImpl class
ms.assetid: 768606da-8b71-417c-a62c-88069ce7730d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d62deeb487fded5895bbd47332a0f8a6ad7bbce6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33102528"
---
# <a name="iaccessorimpl-class"></a>Класс IAccessorImpl
Предоставляет реализацию [IAccessor](https://msdn.microsoft.com/en-us/library/ms719672.aspx) интерфейса.  
  
## <a name="syntax"></a>Синтаксис

```cpp
template <class T, 
          class BindType = ATLBINDINGS,
          class BindingVector = CAtlMap <HACCESSOR hAccessor, BindType* pBindingsStructure>>  
class ATL_NO_VTABLE IAccessorImpl : public IAccessorImplBase<BindType>  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс объекта набора строк или команды.  
  
 `BindType`  
 Устройство хранения для сведения о привязке. Значение по умолчанию — **ATLBINDINGS** структуры (см. раздел atldb.h).  
  
 `BindingVector`  
 Единица хранения сведений о столбце. Значение по умолчанию — [CAtlMap](../../atl/reference/catlmap-class.md) ключевой элемент которого является **HACCESSOR** значение и значение элемента — это указатель на `BindType` структуры.  
  
## <a name="members"></a>Члены  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)|Конструктор.|  
  
### <a name="interface-methods"></a>Методы интерфейса  
  
|||  
|-|-|  
|[AddRefAccessor](../../data/oledb/iaccessorimpl-addrefaccessor.md)|Добавляет существующий метод доступа значение счетчика ссылок.|  
|[CreateAccessor](../../data/oledb/iaccessorimpl-createaccessor.md)|Создает метод доступа из набора привязок.|  
|[GetBindings](../../data/oledb/iaccessorimpl-getbindings.md)|Возвращает привязки из метода доступа.|  
|[ReleaseAccessor](../../data/oledb/iaccessorimpl-releaseaccessor.md)|Освобождает метод доступа.|  
  
## <a name="remarks"></a>Примечания  
 Обязателен для наборов строк и команд. OLE DB требует, чтобы реализовать поставщики **HACCESSOR**, являющееся тег в массив [DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) структуры. **HACCESSOR**s, предоставляемые `IAccessorImpl` являются адреса `BindType` структуры. По умолчанию `BindType` определяется как **ATLBINDINGS** в `IAccessorImpl`в определении шаблона. `BindType` предоставляет механизм, используемый `IAccessorImpl` для отслеживания числа элементов в его **DBBINDING** массива, а также ссылка метода доступа и число флагов.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)