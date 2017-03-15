---
title: "Класс COleLinkingDoc | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleLinkingDoc
dev_langs:
- C++
helpviewer_keywords:
- OLE containers, client items
- COleLinkingDoc class
ms.assetid: 9f547f35-2f95-427f-b9c0-85c31940198b
caps.latest.revision: 24
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
ms.openlocfilehash: acdfde1413d5ff93efc63dbbf211881f71cf624e
ms.lasthandoff: 02/24/2017

---
# <a name="colelinkingdoc-class"></a>Класс COleLinkingDoc
Базовый класс для документов OLE-контейнера, которые поддерживают связывание со встроенными элементами, которые их содержат.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleLinkingDoc : public COleDocument  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleLinkingDoc::COleLinkingDoc](#colelinkingdoc)|Создает объект `COleLinkingDoc`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleLinkingDoc::Register](#register)|Регистрирует документа OLE системные библиотеки DLL.|  
|[COleLinkingDoc::Revoke](#revoke)|Отменяет регистрацию документа.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleLinkingDoc::OnFindEmbeddedItem](#onfindembeddeditem)|Находит указанный внедренный элемент.|  
|[COleLinkingDoc::OnGetLinkedItem](#ongetlinkeditem)|Выполняет поиск указанного связанного элемента.|  
  
## <a name="remarks"></a>Примечания  
 Приложения-контейнера, который поддерживает связывание встроенными элементами называется «контейнер ссылку». [OCLIENT](../../visual-cpp-samples.md) пример приложения является примером контейнера ссылку.  
  
 Если связанный элемент источником является встроенного элемента в другой документ, содержащий документ загрузку для внедренного элемента для редактирования. По этой причине контейнера ссылку должен иметь возможность запускаться другим приложением контейнера, когда пользователь хочет изменить источник связанного элемента. Приложение также должно использовать [COleTemplateServer](../../mfc/reference/coletemplateserver-class.md) класса, чтобы можно было создавать документы при запуске программным способом.  
  
 Чтобы контейнер ссылку контейнера, сформируйте класс документа из `COleLinkingDoc` вместо [COleDocument](../../mfc/reference/coledocument-class.md). Как и в случае любой другой контейнер OLE, необходимо разработать класс для хранения приложения собственных данных, а также внедренные и связанные элементы. Кроме того необходимо разработать структуры данных для хранения данных в собственном. Если определить `CDocItem`-производный класс для собственного приложения данные, можно использовать интерфейс, определяемый `COleDocument` для хранения данных в собственном, а также данных OLE.  
  
 Чтобы разрешить приложению запускаться программно другой контейнер, объявить `COleTemplateServer` объект как член приложения `CWinApp`-производного класса:  
  
 [!code-cpp[NVC_MFCOleContainer&#23;](../../mfc/codesnippet/cpp/colelinkingdoc-class_1.h)]  
  
 В `InitInstance` функцию-член вашей `CWinApp`-производного класса, создайте шаблон документа и укажите вашей `COleLinkingDoc`-производный класс как класс документа:  
  
 [!code-cpp[NVC_MFCOleContainer&#24;](../../mfc/codesnippet/cpp/colelinkingdoc-class_2.cpp)]  
  
 Подключения к `COleTemplateServer` объектов в шаблонах документов путем вызова объекта `ConnectTemplate` функции-члена, а также регистрировать все классы объектов в системе OLE путем вызова **COleTemplateServer::RegisterAll**:  
  
 [!code-cpp[NVC_MFCOleContainer&#25;](../../mfc/codesnippet/cpp/colelinkingdoc-class_3.cpp)]  
  
 Образец `CWinApp`-производный класс определения и `InitInstance` см. в разделе OCLIENT. H и OCLIENT. CPP в образце MFC [OCLIENT](../../visual-cpp-samples.md).  
  
 Дополнительные сведения об использовании `COleLinkingDoc`, см. в статьях [контейнеры: реализация контейнера](../../mfc/containers-implementing-a-container.md) и [контейнеров: Дополнительные функции](../../mfc/containers-advanced-features.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 [COleDocument](../../mfc/reference/coledocument-class.md)  
  
 `COleLinkingDoc`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxole.h  
  
##  <a name="a-namecolelinkingdoca--colelinkingdoccolelinkingdoc"></a><a name="colelinkingdoc"></a>COleLinkingDoc::COleLinkingDoc  
 Создает `COleLinkingDoc` объекта, не создавая связи с OLE системные библиотеки DLL.  
  
```  
COleLinkingDoc();
```  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать метод `Register` функции-члена для информирования OLE документ открыт.  
  
##  <a name="a-nameonfindembeddeditema--colelinkingdoconfindembeddeditem"></a><a name="onfindembeddeditem"></a>COleLinkingDoc::OnFindEmbeddedItem  
 Вызывается средой, чтобы определить, содержит ли документ с указанным именем встроенного элемента OLE.  
  
```  
virtual COleClientItem* OnFindEmbeddedItem(LPCTSTR lpszItemName);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszItemName`  
 Указатель на имя внедренного OLE запрошенного элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на указанный элемент; **NULL** Если элемент не найден.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию выполняет поиск в списке встроенных элементов для элемента с указанным именем (имя сравнение чувствительно к регистру). Переопределите эту функцию, если у вас есть собственный метод хранения или именования внедренные элементы OLE.  
  
##  <a name="a-nameongetlinkeditema--colelinkingdocongetlinkeditem"></a><a name="ongetlinkeditem"></a>COleLinkingDoc::OnGetLinkedItem  
 Вызывается средой, чтобы проверить, содержит ли документ элемент связанного сервера с указанным именем.  
  
```  
virtual COleServerItem* OnGetLinkedItem(LPCTSTR lpszItemName);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszItemName`  
 Указатель на имя связанного OLE запрошенного элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на указанный элемент; **NULL** Если элемент не найден.  
  
### <a name="remarks"></a>Примечания  
 Значение по умолчанию `COleLinkingDoc` реализация всегда возвращает **NULL**. Эта функция будет переопределен в производном классе `COleServerDoc` для поиска в списке сервер OLE-элементы для элемента, связанного с указанным именем (имя сравнивается с учетом регистра). Переопределите эту функцию, если реализован собственный метод хранение и извлечение элементов связанного сервера.  
  
##  <a name="a-nameregistera--colelinkingdocregister"></a><a name="register"></a>COleLinkingDoc::Register  
 Сообщает системе OLE библиотеки DLL, что документ открыт.  
  
```  
BOOL Register(
    COleObjectFactory* pFactory,  
    LPCTSTR lpszPathName);
```  
  
### <a name="parameters"></a>Параметры  
 *pFactory*  
 Указатель на объект фабрики OLE (может быть **NULL**).  
  
 `lpszPathName`  
 Указатель на полный путь документе-контейнере.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если документ успешно зарегистрировано; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Вызов этой функции при создании или открытии файл с именем регистрируемого документа OLE системные библиотеки DLL. Нет необходимости вызывать данную функцию, если документ представляет внедренный элемент.  
  
 При использовании `COleTemplateServer` в приложении, `Register` вызывается для вас `COleLinkingDoc`реализация `OnNewDocument`, `OnOpenDocument`, и `OnSaveDocument`.  
  
##  <a name="a-namerevokea--colelinkingdocrevoke"></a><a name="revoke"></a>COleLinkingDoc::Revoke  
 Сообщает системе OLE библиотеки DLL, что документ больше не открыт.  
  
```  
void Revoke();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для отмены регистрации документа с OLE системные библиотеки DLL.  
  
 Эту функцию следует вызывать при закрытии файл с именем, но обычно не требуется напрямую вызывать. `Revoke`вызывается для вас `COleLinkingDoc`реализация `OnCloseDocument`, `OnNewDocument`, `OnOpenDocument`, и `OnSaveDocument`.  
  
## <a name="see-also"></a>См. также  
 [Пример MFC OCLIENT](../../visual-cpp-samples.md)   
 [Класс COleDocument](../../mfc/reference/coledocument-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CDocTemplate-класс](../../mfc/reference/cdoctemplate-class.md)

