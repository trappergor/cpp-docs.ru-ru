---
title: Класс CSettingsStoreSP | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP::CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP::Create
- AFXSETTINGSSTORE/CSettingsStoreSP::SetRuntimeClass
dev_langs:
- C++
helpviewer_keywords:
- CSettingsStoreSP [MFC], CSettingsStoreSP
- CSettingsStoreSP [MFC], Create
- CSettingsStoreSP [MFC], SetRuntimeClass
ms.assetid: bcd37f40-cfd4-4d17-a5ce-3bfabe995dcc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1852f4e280fa49a2436c421d4669e9d735d66c3b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="csettingsstoresp-class"></a>Класс CSettingsStoreSP
`CSettingsStoreSP` Класс — это вспомогательный класс, который можно использовать для создания экземпляров [CSettingsStore класса](../../mfc/reference/csettingsstore-class.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CSettingsStoreSP  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSettingsStoreSP::CSettingsStoreSP](#csettingsstoresp)|Создает объект `CSettingsStoreSP`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSettingsStoreSP::Create](#create)|Создает экземпляр класса, который является производным от `CSettingsStore`.|  
|[CSettingsStoreSP::SetRuntimeClass](#setruntimeclass)|Задает класс среды выполнения. `Create` Метод использует класс среды выполнения, чтобы определить, какому классу объектов для создания.|  
  
### <a name="data-members"></a>Элементы данных  
  
|name|Описание|  
|----------|-----------------|  
|`m_dwUserData`|Пользовательские данные, хранящиеся в `CSettingsStoreSP` объекта. Ввести эти данные в конструкторе `CSettingsStoreSP` объекта.|  
|`m_pRegistry`|`CSettingsStore`-Производного объекта, `Create` методом.|  
  
## <a name="remarks"></a>Примечания  
 Можно использовать `CSettingsStoreSP` класса для перенаправления всех операций реестра MFC в других местах, например в XML-файл или базу данных. Для этого выполните следующие действия:  
  
1.  Создайте класс (такие как `CMyStore`) и сделайте его производным от `CSettingsStore`.  
  
2.  Используйте [DECLARE_DYNCREATE](run-time-object-model-services.md#declare_dyncreate) и [IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate) макросов с пользовательским `CSettingsStore` класса, чтобы включить динамическое создание.  
  
3.  Переопределение виртуальных функций и реализовать `Read` и `Write` функции в пользовательский класс. Реализуйте другие функциональные возможности для чтения и записи данных в нужное место.  
  
4.  В приложении, вызывать `CSettingsStoreSP::SetRuntimeClass` и передать указатель на [структуры CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) получен из вашего класса.  
  
 Каждый раз, когда платформа обычно будет доступ к реестру, он будет динамически создать экземпляр пользовательского класса и использовать его для чтения или записи данных.  
  
 `CSettingsStoreSP::SetRuntimeClass` использует глобальной статической переменной. Таким образом только один настраиваемое хранилище доступен одновременно.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxsettingsstore.h  
  
##  <a name="create"></a>  CSettingsStoreSP::Create  
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
 Можно использовать метод [CSettingsStoreSP::SetRuntimeClass](#setruntimeclass) для определения типа объекта `CSettingsStoreSP::Create` будет создан. По умолчанию этот метод создает `CSettingsStore` объекта.  
  
 Если вы создаете `CSettingsStore` объекта в режиме администратора, расположение по умолчанию для всех видов доступа реестра HKEY_LOCAL_MACHINE. В противном случае расположение по умолчанию для всех доступ к реестру — HKEY_CURRENT_USER.  
  
 Если `bAdmin` — `TRUE`, приложение должно иметь права администратора. В противном случае операция завершится сбоем при попытке доступа к реестру.  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `Create` метод `CSettingsStoreSP` класса.  
  
 [!code-cpp[NVC_MFC_RibbonApp#33](../../mfc/reference/codesnippet/cpp/csettingsstoresp-class_1.cpp)]  
  
##  <a name="csettingsstoresp"></a>  CSettingsStoreSP::CSettingsStoreSP  
 Создает [CSettingsStoreSP класс](../../mfc/reference/csettingsstoresp-class.md) объекта.  
  
```  
CSettingsStoreSP::CSettingsStoreSP(DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dwUserData`  
 Определяемые пользователем данные, `CSettingsStoreSP` объекта хранилища.  
  
### <a name="remarks"></a>Примечания  
 `CSettingsStoreSP` Объект сохраняет данные из `dwUserData` в переменной защищенный элемент `m_dwUserData`.  
  
##  <a name="setruntimeclass"></a>  CSettingsStoreSP::SetRuntimeClass  
 Задает класс среды выполнения. Метод [CSettingsStoreSP::Create](#create) использует класс среды выполнения для определения типа создаваемого объекта.  
  
```  
static BOOL __stdcall CSettingsStoreSP::SetRuntimeClass(CRuntimeClass* pRTI);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pRTI`  
 Указатель на сведения о классе среды выполнения для класса, производного от [CSettingsStore класса](../../mfc/reference/csettingsstore-class.md).  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` в случае успешного выполнения; `FALSE` Если определить класс с `pRTI` не является производным от `CSettingsStore`.  
  
### <a name="remarks"></a>Примечания  
 Можно использовать [класса CSettingsStoreSP](../../mfc/reference/csettingsstoresp-class.md) для формирования классов из `CSettingsStore`. Используйте метод `SetRuntimeClass` необходимо создать пользовательский класс, производный от объектов `CSettingsStore`.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CSettingsStore](../../mfc/reference/csettingsstore-class.md)
