---
title: "TN016. Использование множественного наследования C++ с MFC | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.inheritance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "МН (множественное наследование)"
  - "множественное наследование, поддержка MFC для"
  - "TN016"
ms.assetid: 4ee27ae1-1410-43a5-b111-b6af9b84535d
caps.latest.revision: 22
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# TN016. Использование множественного наследования C++ с MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Эта заметка описывается использование множественного наследования с классами Microsoft Foundation \(MI\).  Использование MI не требуется с MFC.  MI не используется во всех классах MFC и не требуется создать библиотеку классов.  
  
 Следующие subtopics описывается MI влияет на использование общих идиоматизмов MFC, так и рассматриваются некоторые ограничения MI.  Некоторые из этих ограничений общие ограничения C C\+\+.  Другие накладываются самими архитектурой MFC.  
  
 В конце этого технического примечания вы найдете завершенное приложение MFC, использующем MI.  
  
## CRuntimeClass  
 Механизмы сохранения и динамического создания объектов MFC использует структуру данных [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md) для уникального определения классов.  MFC связывает одну из этих структур с каждым динамическим и\/или сериализуемого класса в приложении.  Эти структуры инициализируются при запуске приложения с помощью специального статических объектов типа `AFX_CLASSINIT`.  
  
 Текущая реализация `CRuntimeClass` не поддерживает данные типа во время выполнения MI.  Это не означает, что невозможно использовать MI в приложении MFC.  Однако имеется несколько обязанности при работе с объектами, имеющими более одного базового класса.  
  
 Метод [CObject::IsKindOf](../Topic/CObject::IsKindOf.md) неправильно определяет тип объекта, если он имеет несколько базовых классов.  Поэтому нельзя использовать [CObject](../Topic/CObject%20Class.md) в качестве виртуального базового класса, а все вызовы функциям элемента `CObject`, такие как [CObject::Serialize](../Topic/CObject::Serialize.md) и [CObject::operator new](../Topic/CObject::operator%20new.md) должны иметь квалификаторы области, чтобы C\+\+ мог различать соответствующий вызов функции.  Когда программа использует MI MFC, внутри класса, содержащего базовый класс `CObject` должны быть классом располагается в списке базовых классов.  
  
 Можно использовать оператор `dynamic_cast`.  Приведение объекта с MI в один из базовых классов принудит компилятору использовать функции указанному в базовом классе.  Для получения дополнительной информации см. [Оператор dynamic\_cast](../cpp/dynamic-cast-operator.md).  
  
## CObject — корень всех классов  
 Все классы, прямо или косвенно от класса `CObject`.  `CObject` отсутствуют данные члена, но они имеют некоторые возможности по умолчанию.  При использовании MI, обычно унаследуете из двух или более `CObject`\- производных классов.  В следующем примере показано, как класс может наследоваться от [CFrameWnd](../mfc/reference/cframewnd-class.md) и [CObList](../mfc/reference/coblist-class.md).  
  
```  
class CListWnd : public CFrameWnd, public CObList  
{  
 ...  
};  
CListWnd myListWnd;  
```  
  
 В этом случае `CObject` включено два раза.  Это означает, что необходимо каким\-то образом различать любая ссылка на методы или операторов `CObject`.  `operator new` и [оператор delete](../Topic/CObject::operator%20delete.md) 2 оператора, необходимо disambiguated.  Другой пример, следующий код вызовет ошибку во время компиляции.  
  
```  
myListWnd.Dump(afxDump);  
    // compile time error, CFrameWnd::Dump or CObList::Dump ?  
```  
  
## Методы Reimplementing CObject  
 При создании нового класса, который имеет два или несколько базовых классов, производных `CObject` необходимо повторно реализовать методы `CObject`, необходимо использовать другие пользователи.  Операторы `new` и `delete` являются обязательными и [Дампа](../Topic/CObject::Dump.md) рекомендуется.  Следующие reimplements примера операторы `new` и `delete` и метод `Dump`:  
  
```  
class CListWnd : public CFrameWnd, public CObList  
{  
public:  
    void* operator new(size_t nSize)  
        { return CFrameWnd::operator new(nSize); }  
    void operator delete(void* p)  
        { CFrameWnd::operator delete(p); }  
  
    void Dump(CDumpContent& dc)  
        { CFrameWnd::Dump(dc);  
          CObList::Dump(dc); }  
     ...  
};  
```  
  
## Виртуальное наследование CObject  
 Может показаться, что виртуального наследования `CObject` решить проблему неоднозначности функции, но это не так.  Так как никакие данные элемента в `CObject`, нет необходимости виртуальное наследование предотвратить несколько копий данных члена базового класса.  В первом примере, рассмотренному ранее, метод `Dump` виртуальный по\-прежнему является неоднозначным, поскольку он реализуется по\-разному в `CFrameWnd` и `CObList`.  Лучший способ удаления неоднозначность выполнять рекомендации, представленные в предыдущем разделе.  
  
## CObject::IsKindOf и времени выполнения:  
 Во время выполнения ввод механизм поддерживается MFC в `CObject` использует макросы `DECLARE_DYNAMIC`, `IMPLEMENT_DYNAMIC`, `DECLARE_DYNCREATE`, `IMPLEMENT_DYNCREATE`, `DECLARE_SERIAL` и `IMPLEMENT_SERIAL`.  Эти макросы могут выполняться проверка типа во время выполнения, чтобы гарантировать безопасные образования производных типов.  
  
 Эти макросы поддерживают только один базовый класс и будут работать в лимитированном способом для умножат наследуемые классы.  Базовый класс указывается в `IMPLEMENT_DYNAMIC` или `IMPLEMENT_SERIAL` должно быть первым \(или располагается\) базового класса.  Это сочетание включит, проверка типа задачи крайнего левого только для базового класса.  Система типов во время выполнения ничего не известно о дополнительных базовых классах.  В следующем примере, время выполнения системы обеспечивают проверку типов для `CFrameWnd`, но ничего не известно о `CObList`.  
  
```  
class CListWnd : public CFrameWnd, public CObList  
{  
    DECLARE_DYNAMIC(CListWnd)  
    ...  
};  
IMPLEMENT_DYNAMIC(CListWnd, CFrameWnd)  
```  
  
## CWnd и сопоставления сообщений  
 Для сопоставления сообщений системы MFC, который будет работать неправильно, 2 дополнительных требований:  
  
-   Должно быть только одно `CWnd` производный от базового класса.  
  
-   `CWnd` производный от базовый класс должен быть первым \(или располагается\) базового класса.  
  
 Ниже приведены некоторые примеры, не будут работать.  
  
```  
class CTwoWindows : public CFrameWnd, public CEdit  
    { ... };  
        // error : two copies of CWnd  
  
class CListEdit : public CObList, public CEdit  
    { ... };  
        // error : CEdit (derived from CWnd) must be first  
```  
  
## Пример программы с помощью MI  
 В следующем примере изолированного приложения состоит из одного класса, производного от `CFrameWnd` и [CWinApp](../mfc/reference/cwinapp-class.md).  Не рекомендуется структура приложения таким образом, но это пример наименьшего приложения MFC с одного класса.  
  
```  
#include <afxwin.h>  
  
class CHelloAppAndFrame : public CFrameWnd, public CWinApp  
{   
public:  
    CHelloAppAndFrame()  
        { }  
  
    // Necessary because of MI disambiguity  
    void* operator new(size_t nSize)  
        { return CFrameWnd::operator new(nSize); }  
    void operator delete(void* p)  
        { CFrameWnd::operator delete(p); }  
  
    // Implementation  
    // CWinApp overrides  
    virtual BOOL InitInstance();  
    // CFrameWnd overrides  
    virtual void PostNcDestroy();  
    afx_msg void OnPaint();  
  
    DECLARE_MESSAGE_MAP()  
  
};  
  
BEGIN_MESSAGE_MAP(CHelloAppAndFrame, CFrameWnd)  
    ON_WM_PAINT()  
END_MESSAGE_MAP()  
  
// because the frame window is not allocated on the heap, we must  
// override PostNCDestroy not to delete the frame object  
void CHelloAppAndFrame::PostNcDestroy()  
{  
    // do nothing (do not call base class)  
}  
  
void CHelloAppAndFrame::OnPaint()  
{  
    CPaintDC dc(this);  
    CRect rect;  
    GetClientRect(rect);  
  
    CString s = "Hello, Windows!";  
    dc.SetTextAlign(TA_BASELINE | TA_CENTER);  
    dc.SetTextColor(::GetSysColor(COLOR_WINDOWTEXT));  
    dc.SetBkMode(TRANSPARENT);  
    dc.TextOut(rect.right / 2, rect.bottom / 2, s);  
}  
  
// Application initialization  
BOOL CHelloAppAndFrame::InitInstance()  
{  
    // first create the main frame  
    if (!CFrameWnd::Create(NULL, "Multiple Inheritance Sample",  
        WS_OVERLAPPEDWINDOW, rectDefault))  
        return FALSE;  
  
    // the application object is also a frame window  
    m_pMainWnd = this;            
    ShowWindow(m_nCmdShow);  
    return TRUE;  
}  
  
CHelloAppAndFrame theHelloAppAndFrame;  
```  
  
## См. также  
 [Технические примечания по номеру](../mfc/technical-notes-by-number.md)   
 [Технические примечания по категории](../mfc/technical-notes-by-category.md)