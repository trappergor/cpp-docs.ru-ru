---
title: "Класс CSettingsStoreSP | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSettingsStoreSP
dev_langs:
- C++
helpviewer_keywords:
- CSettingsStoreSP class
ms.assetid: bcd37f40-cfd4-4d17-a5ce-3bfabe995dcc
caps.latest.revision: 18
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 00131a3c03fdb2c1c1de247a8e1bdcfd9beaf852
ms.lasthandoff: 02/24/2017

---
# <a name="csettingsstoresp-class"></a>Класс CSettingsStoreSP
`CSettingsStoreSP` Класс является вспомогательным классом, который можно использовать для создания экземпляров [CSettingsStore класса](../../mfc/reference/csettingsstore-class.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CSettingsStoreSP  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSettingsStoreSP::CSettingsStoreSP](#csettingsstoresp)|Создает объект `CSettingsStoreSP`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSettingsStoreSP::Create](#create)|Создает экземпляр класса, который является производным от `CSettingsStore`.|  
|[CSettingsStoreSP::SetRuntimeClass](#setruntimeclass)|Задает класс среды выполнения. `Create` Метод использует класс среды выполнения, чтобы определить, какой класс объектов для создания.|  
  
### <a name="data-members"></a>Элементы данных  
  
|Имя|Описание|  
|----------|-----------------|  
|`m_dwUserData`|Пользовательские данные, хранящиеся в `CSettingsStoreSP` объекта. Предоставить эти данные в конструкторе `CSettingsStoreSP` объекта.|  
|`m_pRegistry`|`CSettingsStore`-Производного объекта, `Create` методом.|  
  
## <a name="remarks"></a>Примечания  
 Можно использовать `CSettingsStoreSP` класса для перенаправления всех операций реестра MFC в других местах, например в XML-файл или базу данных. Для этого выполните следующие действия:  
  
1.  Создайте класс (например, `CMyStore`) и сделайте его производным от `CSettingsStore`.  
  
2.  Используйте [DECLARE_DYNCREATE](run-time-object-model-services.md#declare_dyncreate) и [IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate) макросов с пользовательским `CSettingsStore` класса для включения динамического создания.  
  
3.  Переопределение виртуальных функций и реализовать `Read` и `Write` функции в пользовательский класс. Реализуйте другие функциональные возможности для чтения и записи данных в нужном расположении.  
  
4.  В приложении, вызывать `CSettingsStoreSP::SetRuntimeClass` и передать указатель на [структуры CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) получен из вашего класса.  
  
 Каждый раз, когда платформа обычно бы доступ к реестру, она будет динамически создать пользовательский класс и использовать его для чтения или записи данных.  
  
 `CSettingsStoreSP::SetRuntimeClass`использует глобальные статической переменной. Таким образом только одного пользовательского хранилища доступен одновременно.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxsettingsstore.h  
  
##  <a name="a-namecreatea--csettingsstorespcreate"></a><a name="create"></a>CSettingsStoreSP::Create  
 Создает новый экземпляр объекта, который является производным от [CSettingsStore класса](../../mfc/reference/csettingsstore-class.md).  
  
```  
CSettingsStore& CSettingsStoreSP Create(
    BOOL bAdmin,  
    BOOL bReadOnly);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bAdmin`  
 Логический параметр, который определяет, является ли `CSettingsStore` объект создается в режиме администратора.  
  
 [in] `bReadOnly`  
 Логический параметр, который определяет, является ли `CSettingsStore` объекта создается для доступа только для чтения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на вновь созданный `CSettingsStore` объекта.  
  
### <a name="remarks"></a>Примечания  
 Можно использовать метод [CSettingsStoreSP::SetRuntimeClass](#setruntimeclass) , чтобы определить, какой тип объекта `CSettingsStoreSP::Create` будет создан. По умолчанию этот метод создает `CSettingsStore` объекта.  
  
 При создании `CSettingsStore` объекта в режиме администратора, расположение по умолчанию для всех доступ реестра HKEY_LOCAL_MACHINE. В противном случае — расположение по умолчанию для всех доступ к реестру — HKEY_CURRENT_USER.  
  
 Если `bAdmin` — `TRUE`, приложение должно иметь права администратора. В противном случае он завершится ошибкой при попытке доступа к реестру.  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `Create` метод `CSettingsStoreSP` класса.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#33;](../../mfc/reference/codesnippet/cpp/csettingsstoresp-class_1.cpp)]  
  
##  <a name="a-namecsettingsstorespa--csettingsstorespcsettingsstoresp"></a><a name="csettingsstoresp"></a>CSettingsStoreSP::CSettingsStoreSP  
 Создает [CSettingsStoreSP класс](../../mfc/reference/csettingsstoresp-class.md) объекта.  
  
```  
CSettingsStoreSP::CSettingsStoreSP(DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dwUserData`  
 Определяемые пользователем данные, `CSettingsStoreSP` объекта хранилища.  
  
### <a name="remarks"></a>Примечания  
 `CSettingsStoreSP` Объект сохраняет данные из `dwUserData` в защищенный член переменной `m_dwUserData`.  
  
##  <a name="a-namesetruntimeclassa--csettingsstorespsetruntimeclass"></a><a name="setruntimeclass"></a>CSettingsStoreSP::SetRuntimeClass  
 Задает класс среды выполнения. Метод [CSettingsStoreSP::Create](#create) использует класс среды выполнения для определения типа создаваемого объекта.  
  
```  
static BOOL __stdcall CSettingsStoreSP::SetRuntimeClass(CRuntimeClass* pRTI);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pRTI`  
 Указатель на данные класса среды выполнения в класс производным от [CSettingsStore класса](../../mfc/reference/csettingsstore-class.md).  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`в случае успешного выполнения; `FALSE` Если определить класс `pRTI` не является производным от `CSettingsStore`.  
  
### <a name="remarks"></a>Примечания  
 Можно использовать [класса CSettingsStoreSP](../../mfc/reference/csettingsstoresp-class.md) создавать производные классы от `CSettingsStore`. Используйте метод `SetRuntimeClass` необходимо создать пользовательский класс, производный от объектов `CSettingsStore`.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CSettingsStore](../../mfc/reference/csettingsstore-class.md)

