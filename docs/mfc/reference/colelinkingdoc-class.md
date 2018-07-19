---
title: Класс COleLinkingDoc | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9116f736e0bf15ff5ea0594e09b2c044a87c9b78
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/05/2018
ms.locfileid: "37849357"
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
 Приложение-контейнер, который поддерживает связывание с встроенными элементами называется «контейнер ссылку». [OCLIENT](../../visual-cpp-samples.md) пример приложения является примером контейнер ссылку.  
  
 Если связанный элемент источник относится к внедренного элемента в другой документ, содержащий документ загрузку для внедренного элемента для редактирования. По этой причине ссылку контейнер должен быть сможет быть запущено другим приложением контейнера, когда пользователь хочет изменить источник связанного элемента. Приложение также должно использовать [COleTemplateServer](../../mfc/reference/coletemplateserver-class.md) таким образом, чтобы можно было создать документы при запуске программным способом.  
  
 Чтобы контейнер ссылку контейнера, являются производными от класса документа `COleLinkingDoc` вместо [COleDocument](../../mfc/reference/coledocument-class.md). Как и в случае с любым другим контейнером OLE, необходимо разработать класс для хранения приложения собственных данных а также внедренных или связанных элементов. Кроме того необходимо разработать структуры данных для хранения данных в собственном. При определении `CDocItem`-производный класс для собственного приложения данные, можно использовать интерфейс, определяемый `COleDocument` для хранения данных в собственном, а также данных OLE.  
  
 Чтобы разрешить приложению программно запускать другой контейнер, объявить `COleTemplateServer` как член вашего приложения `CWinApp`-производный класс:  
  
 [!code-cpp[NVC_MFCOleContainer#23](../../mfc/codesnippet/cpp/colelinkingdoc-class_1.h)]  
  
 В `InitInstance` функцию-член вашей `CWinApp`-производного класса, создайте шаблон документа и укажите ваш `COleLinkingDoc`-производный класс как класс документа:  
  
 [!code-cpp[NVC_MFCOleContainer#24](../../mfc/codesnippet/cpp/colelinkingdoc-class_2.cpp)]  
  
 Подключение вашей `COleTemplateServer` объекта на шаблоны документов путем вызова объекта `ConnectTemplate` функция-член, а также регистрировать все классы объектов в системе OLE, вызвав `COleTemplateServer::RegisterAll`:  
  
 [!code-cpp[NVC_MFCOleContainer#25](../../mfc/codesnippet/cpp/colelinkingdoc-class_3.cpp)]  
  
 Пример `CWinApp`-производным определения класса и `InitInstance` функции, см. в разделе OCLIENT. H и OCLIENT. CPP, в образце MFC [OCLIENT](../../visual-cpp-samples.md).  
  
 Дополнительные сведения об использовании `COleLinkingDoc`, см. в статьях [контейнеры: реализация контейнера](../../mfc/containers-implementing-a-container.md) и [контейнеры: Дополнительные функции](../../mfc/containers-advanced-features.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 [COleDocument](../../mfc/reference/coledocument-class.md)  
  
 `COleLinkingDoc`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxole.h  
  
##  <a name="colelinkingdoc"></a>  COleLinkingDoc::COleLinkingDoc  
 Создает `COleLinkingDoc` объектом, не начиная обмен данными с OLE системные библиотеки DLL.  
  
```  
COleLinkingDoc();
```  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать `Register` функция-член для информирования OLE, что документ открыт.  
  
##  <a name="onfindembeddeditem"></a>  COleLinkingDoc::OnFindEmbeddedItem  
 Вызывается платформой для определения, содержит ли документ встроенного элемента OLE с указанным именем.  
  
```  
virtual COleClientItem* OnFindEmbeddedItem(LPCTSTR lpszItemName);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszItemName*  
 Указатель на имя внедренного элемента запрошено OLE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на указанный элемент; Значение NULL, если элемент не найден.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию выполняет поиск в списке встроенных элементов для элемента с указанным именем (сравнение имени выполняется с учетом регистра). Переопределите эту функцию, если у вас есть собственный метод хранения и именования внедренные элементы OLE.  
  
##  <a name="ongetlinkeditem"></a>  COleLinkingDoc::OnGetLinkedItem  
 Вызывается платформой для проверки, содержит ли документ элемент связанного сервера с указанным именем.  
  
```  
virtual COleServerItem* OnGetLinkedItem(LPCTSTR lpszItemName);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszItemName*  
 Указатель на имя связанного элемента запрошено OLE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на указанный элемент; Значение NULL, если элемент не найден.  
  
### <a name="remarks"></a>Примечания  
 Значение по умолчанию `COleLinkingDoc` реализация всегда возвращает значение NULL. Эта функция представляет переопределении в производном классе `COleServerDoc` для поиска в списке элементов сервера OLE для связанного элемента с указанным именем (сравнение имени выполняется с учетом регистра). Переопределите эту функцию, если вы реализовали собственные метод хранения и получение элементов связанного сервера.  
  
##  <a name="register"></a>  COleLinkingDoc::Register  
 Сообщает системе OLE библиотеки DLL, что документ открыт.  
  
```  
BOOL Register(
    COleObjectFactory* pFactory,  
    LPCTSTR lpszPathName);
```  
  
### <a name="parameters"></a>Параметры  
 *pFactory*  
 Указатель на объект фабрики OLE (может иметь значение NULL).  
  
 *lpszPathName*  
 Указатель на полный путь документа контейнера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если документ успешно зарегистрирован; в противном случае 0.  
  
### <a name="remarks"></a>Примечания  
 Вызывайте эту функцию при создании или открытии файл с именем для регистрации документа OLE системные библиотеки DLL. Нет необходимости для вызова этой функции в том случае, если документ представляет внедренный элемент.  
  
 Если вы используете `COleTemplateServer` в приложении, `Register` вызывается для вас `COleLinkingDoc`в реализации `OnNewDocument`, `OnOpenDocument`, и `OnSaveDocument`.  
  
##  <a name="revoke"></a>  COleLinkingDoc::Revoke  
 Сообщает системе OLE библиотеки DLL, что документ не открыт.  
  
```  
void Revoke();
```  
  
### <a name="remarks"></a>Примечания  
 Вызывайте эту функцию, чтобы отменить регистрацию документа OLE системные библиотеки DLL.  
  
 Эту функцию следует вызывать при закрытии файл с именем, но обычно не требуется напрямую вызывать. `Revoke` вызывается для вас `COleLinkingDoc`в реализации `OnCloseDocument`, `OnNewDocument`, `OnOpenDocument`, и `OnSaveDocument`.  
  
## <a name="see-also"></a>См. также  
 [Пример MFC OCLIENT](../../visual-cpp-samples.md)   
 [Класс COleDocument](../../mfc/reference/coledocument-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CDocTemplate](../../mfc/reference/cdoctemplate-class.md)
