---
title: "Макросы реестра | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlcom/ATL::_ATL_STATIC_REGISTRY
- atlcom/ATL::DECLARE_LIBID
- atlcom/ATL::DECLARE_NO_REGISTRY
- atlcom/ATL::DECLARE_REGISTRY
- atlcom/ATL::DECLARE_REGISTRY_APPID_RESOURCEID
- atlcom/ATL::DECLARE_REGISTRY_RESOURCE
- atlcom/ATL::DECLARE_REGISTRY_RESOURCEID
dev_langs: C++
helpviewer_keywords: registry, ATL macros
ms.assetid: 3ee041da-c63b-42a4-89cf-2a4b2a6f81ae
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: eada9ed75bd69122523350536d0757e98b31358d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="registry-macros"></a>Макросы реестра
Эти макросы определяют полезный тип средства библиотеки и реестра.  
  
|||  
|-|-|  
|[_ATL_STATIC_REGISTRY](#_atl_static_registry)|Указывает, что код регистрации для объекта в объект во избежание зависимость для библиотеки ATL. БИБЛИОТЕКИ DLL.|  
|[DECLARE_LIBID](#declare_libid)|Предоставляет способ ATL для получения *libid* библиотеки типов.|  
|[DECLARE_NO_REGISTRY](#declare_no_registry)|Позволяет избежать регистрации ATL по умолчанию.|  
|[DECLARE_REGISTRY](#declare_registry)|Вводит или удаляет запись основного объекта в системном реестре.|  
|[DECLARE_REGISTRY_APPID_RESOURCEID](#declare_registry_appid_resourceid)|Указывает сведения, необходимые для автоматической регистрации *appid*.|  
|[DECLARE_REGISTRY_RESOURCE](#declare_registry_resource)|Находит именованный ресурс и запускает скрипт реестра внутри него.|  
|[DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid)|Находит ресурс, заданный идентификатором и запускает скрипт реестра внутри него.|  

## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
  
    
##  <a name="_atl_static_registry"></a>_ATL_STATIC_REGISTRY  
 Символ, который указывает, что требуется создать код регистрации для объекта в объект во избежание зависимость для библиотеки ATL. БИБЛИОТЕКИ DLL.  
  
```
#define _ATL_STATIC_REGISTRY
```  
  
### <a name="remarks"></a>Примечания  
 При определении **ATL_STATIC_REGISTRY**, следует использовать следующий код:  
  
 [!code-cpp[NVC_ATL_EventHandlingSample#5](../../atl/codesnippet/cpp/registry-macros_1.cpp)]  
  
##  <a name="declare_libid"></a>DECLARE_LIBID  
 Предоставляет способ ATL для получения *libid* библиотеки типов.  
  
```
DECLARE_LIBID( libid )
```  
  
### <a name="parameters"></a>Параметры  
 *Идентификатор LIBID*  
 Идентификатор GUID для библиотеки типов.  
  
### <a name="remarks"></a>Примечания  
 Используйте `DECLARE_LIBID` в `CAtlModuleT`-производного класса.  
  
### <a name="example"></a>Пример  
 Проекты ATL без атрибутов созданный мастером будет образец с помощью этого макроса.  
  
##  <a name="declare_no_registry"></a>DECLARE_NO_REGISTRY  
 Используйте `DECLARE_NO_REGISTRY` , если вы хотите избежать любой регистрации ATL по умолчанию для класса, в котором отображается этот макрос.  
  
```
DECLARE_NO_REGISTRY()
```  
  
##  <a name="declare_registry"></a>DECLARE_REGISTRY  
 Вводит стандартный класс регистрации в системный реестр или удаляет его из системного реестра.  
  
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
 [in] `LPCTSTR` , Идентификатор конкретной версии программы.  
  
 *vpid*  
 [in] `LPCTSTR` , Идентификатор программы зависят от версии.  
  
 *nid*  
 [in] Объект **UINT** именно индекс строки ресурса в реестре для использования в качестве описание программы.  
  
 `flags`  
 [in] Объект `DWORD` с программой потоковой модели в реестре. Должен быть одним из следующих значений: **THREADFLAGS_APARTMENT**, **THREADFLAGS_BOTH**, или **AUTPRXFLAG**.  
  
### <a name="remarks"></a>Примечания  
 Стандартная регистрации состоит из идентификатора CLSID, идентификатор программы, идентификатор программы зависят от версии, строку описания и потоковую модель.  
  
 При создании объекта или управлять с помощью мастера добавления класса ATL, мастер автоматически реализует поддержку на основе сценария реестра и добавляет [DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid) макрос в файлы. Если не требуется поддержка реестра на основе сценария, необходимо заменить этот макрос с `DECLARE_REGISTRY`. `DECLARE_REGISTRY`вставляет только пять основных ключей, описанных выше, в реестр. Вручную, необходимо написать код для вставки остальные ключи в реестре.  
  
##  <a name="declare_registry_appid_resourceid"></a>DECLARE_REGISTRY_APPID_RESOURCEID  
 Указывает сведения, необходимые для автоматической регистрации *appid*.  
  
```
DECLARE_REGISTRY_APPID_RESOURCEID(
    resid, 
    appid )
```  
  
### <a name="parameters"></a>Параметры  
 *Идентификатор ресурса*  
 Идентификатор ресурса RGS-файл, который содержит сведения о *appid*.  
  
 *ИД приложения*  
 Идентификатор GUID.  
  
### <a name="remarks"></a>Примечания  
 Используйте `DECLARE_REGISTRY_APPID_RESOURCEID` в `CAtlModuleT`-производного класса.  
  
### <a name="example"></a>Пример  
 Классы, добавляемые в проекты ATL с помощью мастера добавления класса код будет иметь образец с помощью этого макроса.  
  
##  <a name="declare_registry_resource"></a>DECLARE_REGISTRY_RESOURCE  
 Возвращает именованный ресурс, содержащий файл реестра и запускает его для ввода объекты в системный реестр или удалить их из системного реестра.  
  
```
DECLARE_REGISTRY_RESOURCE( x )
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 [in] Строковый идентификатор ресурса.  
  
### <a name="remarks"></a>Примечания  
 При создании объекта или элемента управления с помощью мастера проектов ATL, мастер автоматически реализовать поддержку на основе сценария реестра и добавьте [DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid) макросом, который аналогичен `DECLARE_REGISTRY_RESOURCE`в вашей файлы.  
  
 Кроме того, можно статически связать с компонент реестра ATL (регистратор) для доступа к реестру оптимизированного. Статически связывает код регистратора, добавьте следующую строку в файл stdafx.h:  
  
 [!code-cpp[NVC_ATL_COM#56](../../atl/codesnippet/cpp/registry-macros_2.h)]  
  
 Если вы хотите ATL для замены значений для замены во время выполнения, не указывайте `DECLARE_REGISTRY_RESOURCE` или `DECLARE_REGISTRY_RESOURCEID` макрос. Вместо этого создайте массив **_ATL_REGMAP_ENTRIES** пару структур, где каждая запись содержит заполнитель переменной со значением, замените заполнитель во время выполнения. Затем вызовите [CAtlModule::UpdateRegistryFromResourceD](catlmodule-class.md#updateregistryfromresourced) или [CAtlModule::UpdateRegistryFromResourceS](catlmodule-class.md#updateregistryfromresources), передача массива. Это добавляет все значения замены в **_ATL_REGMAP_ENTRIES** структуры карту замены регистратора.  

  
 Дополнительные сведения о подстановочных параметров и сценариев см. в статье [компонент реестра ATL (регистратор)](../../atl/atl-registry-component-registrar.md).  
  
##  <a name="declare_registry_resourceid"></a>DECLARE_REGISTRY_RESOURCEID  
 То же, что [DECLARE_REGISTRY_RESOURCE](#declare_registry_resource) за исключением того, что он использует, создаваемые мастером **UINT** для идентификации ресурса, а не имя строки.  
  
```
DECLARE_REGISTRY_RESOURCEID( x )
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 [in] Создаваемые мастером идентификатор ресурса.  
  
### <a name="remarks"></a>Примечания  
 При создании объекта или элемента управления с помощью мастера проектов ATL, мастер автоматически реализовать поддержку на основе сценария реестра и добавьте `DECLARE_REGISTRY_RESOURCEID` макрос в файлы.  
  
 Кроме того, можно статически связать с компонент реестра ATL (регистратор) для доступа к реестру оптимизированного. Статически связывает код регистратора, добавьте следующую строку в файл stdafx.h:  
  
 [!code-cpp[NVC_ATL_COM#56](../../atl/codesnippet/cpp/registry-macros_2.h)]  
  
 Если вы хотите ATL для замены значений для замены во время выполнения, не указывайте `DECLARE_REGISTRY_RESOURCE` или `DECLARE_REGISTRY_RESOURCEID` макрос. Вместо этого создайте массив **_ATL_REGMAP_ENTRIES** пару структур, где каждая запись содержит заполнитель переменной со значением, замените заполнитель во время выполнения. Затем вызовите [CAtlModule::UpdateRegistryFromResourceD](catlmodule-class.md#updateregistryfromresourced) или [CAtlModule::UpdateRegistryFromResourceS](catlmodule-class.md#updateregistryfromresources), передача массива. Это добавляет все значения замены в **_ATL_REGMAP_ENTRIES** структуры карту замены регистратора.  

  
 Дополнительные сведения о подстановочных параметров и сценариев см. в статье [компонент реестра ATL (регистратор)](../../atl/atl-registry-component-registrar.md).  
  
## <a name="see-also"></a>См. также  
 [Макросы](../../atl/reference/atl-macros.md)
