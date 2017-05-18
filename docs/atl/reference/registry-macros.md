---
title: "Макросы реестра | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- registry, ATL macros
ms.assetid: 3ee041da-c63b-42a4-89cf-2a4b2a6f81ae
caps.latest.revision: 16
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 3a3abf5ad29b50c7f6708f02fd7c5aa193b3591c
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="registry-macros"></a>Макросы реестра
Эти макросы определяют возможности полезный тип библиотеки и реестра.  
  
|||  
|-|-|  
|[_ATL_STATIC_REGISTRY](#_atl_static_registry)|Указывает, что код регистрации для объекта в объект во избежание зависимость от библиотеки ATL. БИБЛИОТЕКА DLL.|  
|[DECLARE_LIBID](#declare_libid)|Предоставляет способ ATL для получения *libid* библиотеки типов.|  
|[DECLARE_NO_REGISTRY](#declare_no_registry)|Позволяет избежать регистрации ATL по умолчанию.|  
|[DECLARE_REGISTRY](#declare_registry)|Вводит или удаляет запись основного объекта в системном реестре.|  
|[DECLARE_REGISTRY_APPID_RESOURCEID](#declare_registry_appid_resourceid)|Указывает сведения, необходимые для автоматической регистрации *appid*.|  
|[DECLARE_REGISTRY_RESOURCE](#declare_registry_resource)|Выполняет поиск указанного ресурса и запускает сценарий реестра в нем.|  
|[DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid)|Находит ресурс, заданный идентификатором и запускает сценарий реестра в нем.|  

## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcom.h  
  
    
##  <a name="_atl_static_registry"></a>_ATL_STATIC_REGISTRY  
 Символ, указывающий, требуется код регистрации для объекта в объект во избежание зависимость от библиотеки ATL. БИБЛИОТЕКА DLL.  
  
```
#define _ATL_STATIC_REGISTRY
```  
  
### <a name="remarks"></a>Примечания  
 При определении **ATL_STATIC_REGISTRY**, следует использовать следующий код:  
  
 [!code-cpp[NVC_ATL_EventHandlingSample&#5;](../../atl/codesnippet/cpp/registry-macros_1.cpp)]  
  
##  <a name="declare_libid"></a>DECLARE_LIBID  
 Предоставляет способ ATL для получения *libid* библиотеки типов.  
  
```
DECLARE_LIBID( libid )
```  
  
### <a name="parameters"></a>Параметры  
 *Идентификатор LIBID*  
 Идентификатор GUID библиотеки типов.  
  
### <a name="remarks"></a>Примечания  
 Используйте `DECLARE_LIBID` в `CAtlModuleT`-производного класса.  
  
### <a name="example"></a>Пример  
 Атрибуты не созданный мастером ATL-проекты будет пример использования этого макроса.  
  
##  <a name="declare_no_registry"></a>DECLARE_NO_REGISTRY  
 Используйте `DECLARE_NO_REGISTRY` , если вы хотите избежать любой регистрации ATL по умолчанию для класса, в котором находится этот макрос.  
  
```
DECLARE_NO_REGISTRY()
```  
  
##  <a name="declare_registry"></a>DECLARE_REGISTRY  
 Вводит стандартный класс регистрации в системном реестре или удаляет его из системного реестра.  
  
```
DECLARE_REGISTRY(
    class, 
    pid, 
    vpid, 
    nid, 
    flags )
```  
  
### <a name="parameters"></a>Параметры  
 `class`  
 [in] Включено для обеспечения обратной совместимости.  
  
 `pid`  
 [in] `LPCTSTR` Это идентификатор конкретной версии программы.  
  
 *vpid*  
 [in] `LPCTSTR` Это идентификатор программы зависят от версии.  
  
 *nid*  
 [in] Объект **UINT** именно индекс строки ресурса в реестре для использования в качестве описание программы.  
  
 `flags`  
 [in] Объект `DWORD` с программой потоковой модели в реестре. Должен быть одним из следующих значений: **THREADFLAGS_APARTMENT**, **THREADFLAGS_BOTH**, или **AUTPRXFLAG**.  
  
### <a name="remarks"></a>Примечания  
 Стандартная регистрации состоит из CLSID, идентификатор программы, зависящих от версии программы идентификатор, строка описания и потоковую модель.  
  
 При создании объекта или управление с помощью мастера добавления классов ATL, мастер автоматически реализует поддержку реестра на основе сценария и добавляет [DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid) макрос в файлы. Если не требуется поддержка реестра на основе сценария, необходимо заменить этот макрос с `DECLARE_REGISTRY`. `DECLARE_REGISTRY`вставляет только пять основных ключей, описанных выше, в реестр. Необходимо вручную написать код для вставки другие ключи в реестр.  
  
##  <a name="declare_registry_appid_resourceid"></a>DECLARE_REGISTRY_APPID_RESOURCEID  
 Указывает сведения, необходимые для автоматической регистрации *appid*.  
  
```
DECLARE_REGISTRY_APPID_RESOURCEID(
    resid, 
    appid )
```  
  
### <a name="parameters"></a>Параметры  
 *ResID*  
 Идентификатор ресурса RGS-файл, который содержит сведения о *appid*.  
  
 *ИД приложения*  
 Идентификатор GUID.  
  
### <a name="remarks"></a>Примечания  
 Используйте `DECLARE_REGISTRY_APPID_RESOURCEID` в `CAtlModuleT`-производного класса.  
  
### <a name="example"></a>Пример  
 Классы, добавленные в проекты ATL с помощью мастера добавления класса код будет иметь пример использования этого макроса.  
  
##  <a name="declare_registry_resource"></a>DECLARE_REGISTRY_RESOURCE  
 Получает именованный ресурс, содержащий файл реестра и запускает сценарий, введите объекты в системный реестр или удалить их из системного реестра.  
  
```
DECLARE_REGISTRY_RESOURCE( x )
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 [in] Строковый идентификатор ресурса.  
  
### <a name="remarks"></a>Примечания  
 При создании объекта или управлять с помощью мастера проектов ATL, мастер автоматически реализовать поддержку на основе сценария реестра и добавьте [DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid) макросом, который аналогичен `DECLARE_REGISTRY_RESOURCE`, к файлам.  
  
 Можно статически связать с компонент реестра ATL (регистратор) для доступа к реестру оптимизированного. Статически связывает код регистратора, добавьте следующую строку в файл stdafx.h:  
  
 [!code-cpp[NVC_ATL_COM&#56;](../../atl/codesnippet/cpp/registry-macros_2.h)]  
  
 Если требуется ATL для замены значений для замены во время выполнения, не указывайте `DECLARE_REGISTRY_RESOURCE` или `DECLARE_REGISTRY_RESOURCEID` макрос. Вместо этого создайте массив **_ATL_REGMAP_ENTRIES** структуры, где каждая запись содержит переменную местозаполнитель в паре со значением, замените заполнитель во время выполнения. Затем вызовите [CAtlModule::UpdateRegistryFromResourceD](catlmodule-class.md#updateregistryfromresourced) или [CAtlModule::UpdateRegistryFromResourceS](catlmodule-class.md#updateregistryfromresources), передав массив. Это добавит все значения замены в **_ATL_REGMAP_ENTRIES** структуры карты замены регистратора.  

  
 Дополнительные сведения о подстановочных параметров и сценариев см. в статье [компонент реестра ATL (регистратор)](../../atl/atl-registry-component-registrar.md).  
  
##  <a name="declare_registry_resourceid"></a>DECLARE_REGISTRY_RESOURCEID  
 То же, что [DECLARE_REGISTRY_RESOURCE](#declare_registry_resource) за исключением того, что он использует, создаваемые мастером **UINT** для определения ресурса, а не имя строки.  
  
```
DECLARE_REGISTRY_RESOURCEID( x )
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 [in] Создаваемые мастером идентификатор ресурса.  
  
### <a name="remarks"></a>Примечания  
 При создании объекта или управлять с помощью мастера проектов ATL, мастер автоматически реализовать поддержку на основе сценария реестра и добавьте `DECLARE_REGISTRY_RESOURCEID` макрос в файлы.  
  
 Можно статически связать с компонент реестра ATL (регистратор) для доступа к реестру оптимизированного. Статически связывает код регистратора, добавьте следующую строку в файл stdafx.h:  
  
 [!code-cpp[NVC_ATL_COM&#56;](../../atl/codesnippet/cpp/registry-macros_2.h)]  
  
 Если требуется ATL для замены значений для замены во время выполнения, не указывайте `DECLARE_REGISTRY_RESOURCE` или `DECLARE_REGISTRY_RESOURCEID` макрос. Вместо этого создайте массив **_ATL_REGMAP_ENTRIES** структуры, где каждая запись содержит переменную местозаполнитель в паре со значением, замените заполнитель во время выполнения. Затем вызовите [CAtlModule::UpdateRegistryFromResourceD](catlmodule-class.md#updateregistryfromresourced) или [CAtlModule::UpdateRegistryFromResourceS](catlmodule-class.md#updateregistryfromresources), передав массив. Это добавит все значения замены в **_ATL_REGMAP_ENTRIES** структуры карты замены регистратора.  

  
 Дополнительные сведения о подстановочных параметров и сценариев см. в статье [компонент реестра ATL (регистратор)](../../atl/atl-registry-component-registrar.md).  
  
## <a name="see-also"></a>См. также  
 [Макросы](../../atl/reference/atl-macros.md)

