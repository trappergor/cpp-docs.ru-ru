---
title: "Класс COleLinkingDoc | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleLinkingDoc
- AFXOLE/COleLinkingDoc
- AFXOLE/COleLinkingDoc::COleLinkingDoc
- AFXOLE/COleLinkingDoc::Register
- AFXOLE/COleLinkingDoc::Revoke
- AFXOLE/COleLinkingDoc::OnFindEmbeddedItem
- AFXOLE/COleLinkingDoc::OnGetLinkedItem
dev_langs:
- C++
helpviewer_keywords:
- COleLinkingDoc [MFC], COleLinkingDoc
- COleLinkingDoc [MFC], Register
- COleLinkingDoc [MFC], Revoke
- COleLinkingDoc [MFC], OnFindEmbeddedItem
- COleLinkingDoc [MFC], OnGetLinkedItem
ms.assetid: 9f547f35-2f95-427f-b9c0-85c31940198b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 611d09a12da1d2ebf6fcae8d7573cc48a5318f97
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="colelinkingdoc-class"></a>Класс COleLinkingDoc
Базовый класс для документов OLE-контейнера, которые поддерживают связывание со встроенными элементами, которые их содержат.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleLinkingDoc : public COleDocument  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleLinkingDoc::COleLinkingDoc](#colelinkingdoc)|Создает объект `COleLinkingDoc`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleLinkingDoc::Register](#register)|Регистрирует документа OLE системные библиотеки DLL.|  
|[COleLinkingDoc::Revoke](#revoke)|Отменяет регистрацию документа.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleLinkingDoc::OnFindEmbeddedItem](#onfindembeddeditem)|Находит указанный внедренный элемент.|  
|[COleLinkingDoc::OnGetLinkedItem](#ongetlinkeditem)|Выполняет поиск указанного связанного элемента.|  
  
## <a name="remarks"></a>Примечания  
 Приложения-контейнера, который поддерживает связывание встроенными элементами, называется «контейнером ссылку». [OCLIENT](../../visual-cpp-samples.md) образец приложения является примером контейнера ссылку.  
  
 Если связанный элемент источником является встроенного элемента в другой документ, содержащий документ загрузку для внедренного элемента для редактирования. По этой причине контейнера ссылку необходимо иметь возможность запускаться другим приложением контейнера, когда пользователь хочет изменить источник связанный элемент. Приложение должно использовать также [COleTemplateServer](../../mfc/reference/coletemplateserver-class.md) класса, чтобы можно было создать документов при запуске программными средствами.  
  
 Чтобы контейнер ссылку контейнера, являются производными класса документа из `COleLinkingDoc` вместо [COleDocument](../../mfc/reference/coledocument-class.md). Как и в случае с любым другим контейнером OLE, необходимо создать класс для хранения приложения собственных данных, а также внедренные и связанные элементы. Кроме того необходимо разработать структуры данных для хранения данных в собственном. Если определить `CDocItem`-производный класс для собственного приложения данные, можно использовать интерфейс, определяемый `COleDocument` для хранения данных в собственном, а также данные OLE.  
  
 Чтобы разрешить приложение для запуска с другой контейнер программными средствами, объявите `COleTemplateServer` как член приложения `CWinApp`-производного класса:  
  
 [!code-cpp[NVC_MFCOleContainer#23](../../mfc/codesnippet/cpp/colelinkingdoc-class_1.h)]  
  
 В `InitInstance` функцию-член вашей `CWinApp`-производного класса, создать шаблон документа и указать вашей `COleLinkingDoc`-производный класс как класс документа:  
  
 [!code-cpp[NVC_MFCOleContainer#24](../../mfc/codesnippet/cpp/colelinkingdoc-class_2.cpp)]  
  
 Подключиться к `COleTemplateServer` объект шаблоны документов путем вызова объекта `ConnectTemplate` функции-члена, а также регистрировать все классы объектов в системе OLE путем вызова **COleTemplateServer::RegisterAll**:  
  
 [!code-cpp[NVC_MFCOleContainer#25](../../mfc/codesnippet/cpp/colelinkingdoc-class_3.cpp)]  
  
 Образец `CWinApp`-производный класс определения и `InitInstance` см. в разделе OCLIENT. H и OCLIENT. CPP в образце MFC [OCLIENT](../../visual-cpp-samples.md).  
  
 Дополнительные сведения об использовании `COleLinkingDoc`, см. в статьях [контейнеры: реализация контейнера](../../mfc/containers-implementing-a-container.md) и [контейнеры: Дополнительные функции](../../mfc/containers-advanced-features.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 [COleDocument](../../mfc/reference/coledocument-class.md)  
  
 `COleLinkingDoc`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxole.h  
  
##  <a name="colelinkingdoc"></a>COleLinkingDoc::COleLinkingDoc  
 Создает `COleLinkingDoc` объекта, не создавая обмен данными с OLE системные библиотеки DLL.  
  
```  
COleLinkingDoc();
```  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать метод `Register` функции-члена для информирования OLE документ открыт.  
  
##  <a name="onfindembeddeditem"></a>COleLinkingDoc::OnFindEmbeddedItem  
 Вызывается платформой для определения, содержит ли документ с указанным именем встроенного элемента OLE.  
  
```  
virtual COleClientItem* OnFindEmbeddedItem(LPCTSTR lpszItemName);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszItemName`  
 Указатель на имя внедренного OLE запрошенного элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на указанный элемент; **NULL** Если элемент не найден.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию выполняет список внедренных элементов для элемента с указанным именем (сравнение имени учитывается регистр символов). Переопределите эту функцию, если у вас есть собственный метод хранения и именования внедренные элементы OLE.  
  
##  <a name="ongetlinkeditem"></a>COleLinkingDoc::OnGetLinkedItem  
 Вызывается платформой, чтобы проверить, содержит ли документ элемент связанного сервера с указанным именем.  
  
```  
virtual COleServerItem* OnGetLinkedItem(LPCTSTR lpszItemName);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszItemName`  
 Указатель на имя связанного OLE запрошенного элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на указанный элемент; **NULL** Если элемент не найден.  
  
### <a name="remarks"></a>Примечания  
 Значение по умолчанию `COleLinkingDoc` реализация всегда возвращает **NULL**. Эта функция будет переопределен в производном классе `COleServerDoc` для поиска в списке сервера OLE-элементы для связанного элемента с указанным именем (сравнение имени учитывается регистр символов). Переопределите эту функцию, если был реализован собственный метод хранения и извлечения элементов связанного сервера.  
  
##  <a name="register"></a>COleLinkingDoc::Register  
 Сообщает системе OLE библиотек DLL, что документ открыт.  
  
```  
BOOL Register(
    COleObjectFactory* pFactory,  
    LPCTSTR lpszPathName);
```  
  
### <a name="parameters"></a>Параметры  
 *pFactory*  
 Указатель на объект фабрики OLE (может быть **NULL**).  
  
 `lpszPathName`  
 Указатель на полный путь документа-контейнера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если документ успешно зарегистрирован; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Вызывайте эту функцию при создании или открытии файл с именем регистрируемого документа с OLE системные библиотеки DLL. Нет необходимости вызывать эту функцию, если документ представляет встроенного элемента.  
  
 При использовании `COleTemplateServer` в вашем приложении `Register` вызывается для вас `COleLinkingDoc`реализация `OnNewDocument`, `OnOpenDocument`, и `OnSaveDocument`.  
  
##  <a name="revoke"></a>COleLinkingDoc::Revoke  
 Сообщает системе OLE библиотек DLL, что документ больше не открыт.  
  
```  
void Revoke();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для отмены регистрации документа с OLE системные библиотеки DLL.  
  
 Эту функцию следует вызывать при закрытии файл с именем, но обычно не требуется вызывать его напрямую. `Revoke`вызывается для вас `COleLinkingDoc`реализация `OnCloseDocument`, `OnNewDocument`, `OnOpenDocument`, и `OnSaveDocument`.  
  
## <a name="see-also"></a>См. также  
 [Пример MFC OCLIENT](../../visual-cpp-samples.md)   
 [Класс COleDocument](../../mfc/reference/coledocument-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CDocTemplate](../../mfc/reference/cdoctemplate-class.md)
