---
title: "Класс CSnapInPropertyPageImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSnapInPropertyPageImpl
- ATLSNAP/ATL::CSnapInPropertyPageImpl
- ATLSNAP/ATL::CSnapInPropertyPageImpl::CSnapInPropertyPageImpl
- ATLSNAP/ATL::CSnapInPropertyPageImpl::CancelToClose
- ATLSNAP/ATL::CSnapInPropertyPageImpl::Create
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnApply
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnHelp
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnKillActive
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnQueryCancel
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnReset
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnSetActive
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnWizardBack
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnWizardFinish
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnWizardNext
- ATLSNAP/ATL::CSnapInPropertyPageImpl::QuerySiblings
- ATLSNAP/ATL::CSnapInPropertyPageImpl::SetModified
- ATLSNAP/ATL::CSnapInPropertyPageImpl::m_psp
dev_langs: C++
helpviewer_keywords:
- snap-ins, property pages
- snap-ins
- property pages, ATL
- CSnapInPropertyPageImpl class
ms.assetid: 75bdce5a-985e-4166-bd44-493132e023c4
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 230ebd2543a559712d491d5acacdbc1f660b3450
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="csnapinpropertypageimpl-class"></a>Класс CSnapInPropertyPageImpl
Этот класс предоставляет методы для реализации объекта страницы свойств оснастки.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
CSnapInPropertyPageImpl : public CDialogImplBase
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSnapInPropertyPageImpl::CSnapInPropertyPageImpl](#csnapinpropertypageimpl)|Конструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSnapInPropertyPageImpl::CancelToClose](#canceltoclose)|Изменяет состояние **ОК** и **отменить** кнопки.|  
|[CSnapInPropertyPageImpl::Create](#create)|Инициализирует только что созданный объект `CSnapInPropertyPageImpl` объекта.|  
|[CSnapInPropertyPageImpl::OnApply](#onapply)|Вызывается платформой, когда пользователь щелкает **применить** кнопки при использовании листа свойств мастера.|  
|[CSnapInPropertyPageImpl::OnHelp](#onhelp)|Вызывается платформой, когда пользователь щелкает **справки** кнопки при использовании листа свойств мастера.|  
|[CSnapInPropertyPageImpl::OnKillActive](#onkillactive)|Вызывается платформой, когда текущая страница больше не активна.|  
|[CSnapInPropertyPageImpl::OnQueryCancel](#onquerycancel)|Вызывается платформой, когда пользователь щелкает **отменить** кнопки и до отмены.|  
|[CSnapInPropertyPageImpl::OnReset](#onreset)|Вызывается платформой, когда пользователь щелкает **Сброс** кнопки при использовании листа свойств мастера.|  
|[CSnapInPropertyPageImpl::OnSetActive](#onsetactive)|Вызывается платформой, когда текущая страница становится активным.|  
|[CSnapInPropertyPageImpl::OnWizardBack](#onwizardback)|Вызывается платформой, когда пользователь щелкает **обратно** кнопки при использовании листа свойств мастера.|  
|[CSnapInPropertyPageImpl::OnWizardFinish](#onwizardfinish)|Вызывается платформой, когда пользователь щелкает **Готово** кнопки при использовании листа свойств мастера.|  
|[CSnapInPropertyPageImpl::OnWizardNext](#onwizardnext)|Вызывается платформой, когда пользователь щелкает `Next` кнопки при использовании листа свойств мастера.|  
|[CSnapInPropertyPageImpl::QuerySiblings](#querysiblings)|Пересылает текущее сообщение для всех страниц свойств.|  
|[CSnapInPropertyPageImpl::SetModified](#setmodified)|Вызов активация и деактивация **применить** кнопки.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSnapInPropertyPageImpl::m_psp](#m_psp)|Windows **PROPSHEETPAGE** структура, используемая `CSnapInPropertyPageImpl` объекта.|  
  
## <a name="remarks"></a>Примечания  
 `CSnapInPropertyPageImpl`Предоставляет базовую реализацию для объекта страницы свойств оснастки. Основные возможности страницы свойств оснастки реализуются с помощью нескольких разных интерфейсов и сопоставления типов.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CDialogImplBase`  
  
 `CSnapInPropertyPageImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlsnap.h  
  
##  <a name="canceltoclose"></a>CSnapInPropertyPageImpl::CancelToClose  
 Эта функция вызывается после неустранимой изменений данных на странице модальную страницу свойств.  
  
```
void CancelToClose();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция приведет к изменению **ОК** кнопки **закрыть** и отключить **отменить** кнопки. Это изменение оповещения пользователя, что изменение является постоянной, а изменения не может быть отменено.  
  
 `CancelToClose` Функция-член не выполняет никаких действий, в немодальный лист свойств, так как нет немодальный лист свойств **отменить** кнопку по умолчанию.  
  
##  <a name="csnapinpropertypageimpl"></a>CSnapInPropertyPageImpl::CSnapInPropertyPageImpl  
 Создает объект `CSnapInPropertyPageImpl`.  
  
```
CSnapInPropertyPageImpl(LPCTSTR lpszTitle = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszTitle`  
 [in] Заголовок страницы свойств.  
  
### <a name="remarks"></a>Примечания  
 Чтобы инициализировать базовой структуры, вызовите [CSnapInPropertyPageImpl::Create](#create).  
  
##  <a name="create"></a>CSnapInPropertyPageImpl::Create  
 Эта функция вызывается для инициализации базовую структуру страницы свойств.  
  
```
HPROPSHEETPAGE Create();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор **PROPSHEETPAGE** структуру, содержащую атрибуты только что созданный свойств.  
  
### <a name="remarks"></a>Примечания  
 Сначала следует вызвать метод [CSnapInPropertyPageImpl::CSnapInPropertyPageImpl](#csnapinpropertypageimpl) перед вызовом этой функции.  
  
##  <a name="m_psp"></a>CSnapInPropertyPageImpl::m_psp  
 `m_psp`— это структура, члены которой хранения характеристики **PROPSHEETPAGE**.  
  
```
PROPSHEETPAGE m_psp;
```  
  
### <a name="remarks"></a>Примечания  
 Используйте эту структуру для инициализации внешний вид страницы свойств, после его создания.  
  
 Дополнительные сведения об этой структуры, в том числе список его элементов. в разделе [PROPSHEETPAGE](http://msdn.microsoft.com/library/aa815151) в Windows SDK.  
  
##  <a name="onapply"></a>CSnapInPropertyPageImpl::OnApply  
 Эта функция-член вызывается, когда пользователь щелкает **ОК** или **применить** кнопки.  
  
```
BOOL OnApply();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если эти изменения принимаются; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Перед `OnApply` может быть вызван платформой, был вызван `SetModified` и задайте для его параметра **TRUE**. Это активирует **применить** кнопку по мере внесения изменений на странице свойств.  
  
 Переопределить эту функцию-член для указания принимает программы, когда пользователь щелкает **применить** кнопки. При переопределении метода, функция должна возвращать **TRUE** для принятия изменений и **FALSE** для предотвращения изменения вступают в силу.  
  
 Реализация по умолчанию `OnApply` возвращает **TRUE**.  
  
##  <a name="onhelp"></a>CSnapInPropertyPageImpl::OnHelp  
 Эта функция-член вызывается, когда пользователь щелкает **справки** кнопки для страницы свойств.  
  
```
void OnHelp();
```  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию-член для отображения справки для страницы свойств.  
  
##  <a name="onkillactive"></a>CSnapInPropertyPageImpl::OnKillActive  
 Эта функция-член вызывается в том случае, когда страница больше не является активной.  
  
```
BOOL OnKillActive();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если данные были успешно обновлены; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию-член для выполнения задач проверки специальных данных.  
  
##  <a name="onquerycancel"></a>CSnapInPropertyPageImpl::OnQueryCancel  
 Эта функция-член вызывается, когда пользователь щелкает **отменить** кнопку и до отмены было выполнено действие.  
  
```
BOOL OnQueryCancel();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, чтобы разрешить операцию "Отмена". в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Переопределить эту функцию-член для указания действия программа принимает, когда пользователь щелкает **отменить** кнопки.  
  
 Реализация по умолчанию `OnQueryCancel` возвращает **TRUE**.  
  
##  <a name="onreset"></a>CSnapInPropertyPageImpl::OnReset  
 Эта функция-член вызывается, когда пользователь щелкает **отменить** кнопки.  
  
```
void OnReset();
```  
  
### <a name="remarks"></a>Примечания  
 Когда эта функция вызывается, изменяется на все страницы свойств, которые были сделаны ранее щелкнув пользователем **применить** кнопка не учитываются, и окно свойств сохраняет фокус.  
  
 Переопределить эту функцию-член для указания программа принимает, когда пользователь щелкает **отменить** кнопки.  
  
##  <a name="onsetactive"></a>CSnapInPropertyPageImpl::OnSetActive  
 Эта функция-член вызывается в том случае, когда страница выбранного пользователем и станет активной.  
  
```
BOOL OnSetActive();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если страницы был успешно задан активно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию-член для выполнения задач при активации страницы. Переопределение функции-члена следует вызывать версию по умолчанию перед выполнением какой-либо другой обработки.  
  
 Реализация по умолчанию возвращает **TRUE**.  
  
##  <a name="onwizardback"></a>CSnapInPropertyPageImpl::OnWizardBack  
 Эта функция-член вызывается, когда пользователь щелкает **обратно** кнопки с помощью мастера.  
  
```
BOOL OnWizardBack();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
-   0 для автоматического перехода на предыдущую страницу.  
  
-   значение -1, чтобы предотвратить изменение страницы.  
  
 Чтобы перейти на страницу, отличном от того, далее, возвращайте идентификатор для отображения диалогового окна.  
  
### <a name="remarks"></a>Примечания  
 Переопределить эту функцию-член для указания некоторые действия, когда должен выполнить пользователь **обратно** кнопки.  
  
##  <a name="onwizardfinish"></a>CSnapInPropertyPageImpl::OnWizardFinish  
 Эта функция-член вызывается, когда пользователь щелкает **Готово** кнопки с помощью мастера.  
  
```
BOOL OnWizardFinish();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если окно свойств уничтожается после завершения работы мастера; в противном случае значение равно нулю.  
  
### <a name="remarks"></a>Примечания  
 Переопределить эту функцию-член для указания некоторые действия, когда должен выполнить пользователь **Готово** кнопки.  
  
##  <a name="onwizardnext"></a>CSnapInPropertyPageImpl::OnWizardNext  
 Эта функция-член вызывается, когда пользователь щелкает `Next` кнопки с помощью мастера.  
  
```
BOOL OnWizardNext();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
-   0, чтобы автоматически перейти на следующую страницу.  
  
-   значение -1, чтобы предотвратить изменение страницы.  
  
 Чтобы перейти на страницу, отличном от того, далее, возвращайте идентификатор для отображения диалогового окна.  
  
### <a name="remarks"></a>Примечания  
 Переопределить эту функцию-член для указания некоторые действия, когда должен выполнить пользователь `Next` кнопки.  
  
##  <a name="querysiblings"></a>CSnapInPropertyPageImpl::QuerySiblings  
 Вызовите эту функцию-член для пересылки сообщения для каждой страницы в окне свойств.  
  
```
LRESULT QuerySiblings(WPARAM wParam, LPARAM lParam);
```  
  
### <a name="parameters"></a>Параметры  
 `wParam`  
 [in] Указывает Дополнительные сведения, зависящие от сообщения.  
  
 `lParam`  
 [in] Указывает Дополнительные сведения, зависящие от сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если не следует перенаправить сообщение на следующую страницу свойств; в противном случае значение равно нулю.  
  
### <a name="remarks"></a>Примечания  
 Если страница возвращает ненулевое значение, окно свойств не отправляет сообщения на последующих страницах.  
  
##  <a name="setmodified"></a>CSnapInPropertyPageImpl::SetModified  
 Вызовите эту функцию-член для включения или отключения **применить** кнопки в зависимости от того, следует ли применять параметры на странице свойств для соответствующего внешнего объекта.  
  
```
void SetModified(BOOL bChanged = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `bChanged`  
 [in] **TRUE** для указания, что параметры страницы свойств были изменены с момента последнего они были применены; **FALSE** для указания, что были применены параметры страницы свойств, или следует игнорировать.  
  
### <a name="remarks"></a>Примечания  
 Окно свойств отслеживает отслеживания, из которых страниц «грязных», то есть, страницы свойств, для которых был вызван **SetModified (TRUE)**. **Применить** всегда активируется кнопка при вызове метода **SetModified (TRUE)** для одной из страниц. **Применить** кнопка будет недоступна, при вызове **SetModified (FALSE)** для одной из страниц, но только если ни один из других страниц является «грязным».  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)
