---
title: "Обработка событий в COM | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COM, события"
  - "объявление событий"
  - "объявление событий, обработка событий в модели COM"
  - "объявление событий, в COM"
  - "обработчики событий"
  - "обработчики событий, COM"
  - "обработка событий"
  - "обработка событий, сведения об обработке событий"
  - "обработка событий, COM"
  - "приемники событий, в обработке событий"
  - "приемники событий, совпадение имени и подписи"
  - "источники событий, в обработке событий"
  - "подключение событий"
ms.assetid: 6b4617d4-a58e-440c-a8a6-1ad1c715b2bb
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Обработка событий в COM
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Для обработки событий COM необходимо настроить источник и приемник событий с помощью атрибутов [event\_source](../windows/event-source.md) и [event\_receiver](../windows/event-receiver.md) соответственно, указав `type`\=**com**.  Эти атрибуты вводят соответствующий код для пользовательского, сдвоенного интерфейса и интерфейса диспетчеризации, чтобы позволить классам, к которым они применяются, запускать и обрабатывать события через точки подключения COM.  
  
## Объявление событий  
 В классе источника событий используйте в объявлении интерфейса ключевое слово [\_\_event](../cpp/event.md), чтобы объявить методы интерфейса в качестве событий.  События этого интерфейса запускаются при вызове их в качестве методов интерфейса.  Методы в интерфейсах событий могут иметь нуль или более параметров \(все они должны являться параметрами **in**\).  Возвращаемый тип может быть пустым или любым целочисленным типом.  
  
## Определение обработчиков событий  
 В классе приемника событий необходимо указать обработчики событий, которые представляют собой методы с подписями \(возвращаемые типы, соглашения о вызовах и аргументы\), соответствующие событию, которое они будут обрабатывать.  Для событий модели COM соглашения о вызове не должны совпадать; см. подробности в разделе [События модели COM, зависимые от макета](#vcconeventhandlingincomanchorlayoutdependentcomevents).  
  
## Прикрепление обработчиков событий к событиям  
 Также в классе приемника событий следует использовать встроенную функцию [\_\_hook](../cpp/hook.md), чтобы связать события с обработчиками, и функцию [\_\_unhook](../cpp/unhook.md), чтобы разъединить их.  Можно прикрепить несколько событий к обработчику событий либо несколько обработчиков событий к одному событию.  
  
> [!NOTE]
>  Как правило, существует два метода предоставления приемнику событий COM доступа к определениям интерфейса исходного кода событий.  Во\-первых, как показано ниже, можно предоставить общий доступ к одному файлу заголовка.  Во\-вторых, можно использовать директиву [\#import](../Topic/%23import%20Directive%20\(C++\).md) с квалификатором импорта `embedded_idl`, чтобы библиотека типов исходного кода событий была записана в TLH\-файл с сохранением созданного атрибутом кода.  
  
## Запуск событий  
 Для запуска события достаточно вызвать метод в интерфейсе, объявленном с использованием ключевого слова `__event` в классе исходного кода событий.  Если обработчики прикреплены к событию, они будут вызваны.  
  
### Код события COM  
 В следующем примере демонстрируется запуск события в COM\-классе.  Для компиляции и выполнения примера см. комментарии в коде.  
  
```  
// evh_server.h  
#pragma once  
  
[ dual, uuid("00000000-0000-0000-0000-000000000001") ]  
__interface IEvents {  
   [id(1)] HRESULT MyEvent([in] int value);  
};  
  
[ dual, uuid("00000000-0000-0000-0000-000000000002") ]  
__interface IEventSource {  
   [id(1)] HRESULT FireEvent();  
};  
  
class DECLSPEC_UUID("530DF3AD-6936-3214-A83B-27B63C7997C4") CSource;  
```  
  
 Затем сервер.  
  
```  
// evh_server.cpp  
// compile with: /LD  
// post-build command: Regsvr32.exe /s evh_server.dll  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
#include "evh_server.h"  
  
[ module(dll, name="EventSource", uuid="6E46B59E-89C3-4c15-A6D8-B8A1CEC98830") ];  
  
[coclass, event_source(com), uuid("530DF3AD-6936-3214-A83B-27B63C7997C4")]  
class CSource : public IEventSource {  
public:  
   __event __interface IEvents;   
  
   HRESULT FireEvent() {  
      __raise MyEvent(123);  
      return S_OK;  
   }  
};  
```  
  
 Затем клиент.  
  
```  
// evh_client.cpp  
// compile with: /link /OPT:NOREF  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
#include <stdio.h>  
#include "evh_server.h"  
  
[ module(name="EventReceiver") ];  
  
[ event_receiver(com) ]  
class CReceiver {  
public:  
   HRESULT MyHandler1(int nValue) {  
      printf_s("MyHandler1 was called with value %d.\n", nValue);  
      return S_OK;  
   }  
  
   HRESULT MyHandler2(int nValue) {  
      printf_s("MyHandler2 was called with value %d.\n", nValue);  
      return S_OK;  
   }  
  
   void HookEvent(IEventSource* pSource) {  
      __hook(&IEvents::MyEvent, pSource, &CReceiver::MyHandler1);  
      __hook(&IEvents::MyEvent, pSource, &CReceiver::MyHandler2);  
   }  
  
   void UnhookEvent(IEventSource* pSource) {  
      __unhook(&IEvents::MyEvent, pSource, &CReceiver::MyHandler1);  
      __unhook(&IEvents::MyEvent, pSource, &CReceiver::MyHandler2);  
   }  
};  
  
int main() {  
   // Create COM object  
   CoInitialize(NULL);  
   {  
      IEventSource* pSource = 0;  
      HRESULT hr = CoCreateInstance(__uuidof(CSource), NULL,         CLSCTX_ALL, __uuidof(IEventSource), (void **) &pSource);  
      if (FAILED(hr)) {  
         return -1;  
      }  
  
      // Create receiver and fire event  
      CReceiver receiver;  
      receiver.HookEvent(pSource);  
      pSource->FireEvent();  
      receiver.UnhookEvent(pSource);  
   }  
   CoUninitialize();  
   return 0;  
}  
```  
  
### Вывод  
  
```  
MyHandler1 was called with value 123.  
MyHandler2 was called with value 123.  
```  
  
##  <a name="vcconeventhandlingincomanchorlayoutdependentcomevents"></a> Зависимые от макета события COM  
 Зависимость от макета становится проблемой только в программировании COM.  При обработке событий в собственном и управляемом коде подписи \(возвращаемый тип, соглашение о вызовах и аргументы\) обработчиков должны соответствовать их событиям, однако имена обработчиков не обязательно должны соответствовать событиям.  
  
 Однако при обработке событий в модели COM, если параметру *layout\_dependent* **приемника\-событий** присвоено значение **true**, принудительно используются соответствующие имя и подпись.  Это означает, что имена и подписи обработчиков в приемнике событий должны точно соответствовать именам и подписям событий, к которым они прикреплены.  
  
 Если параметру *layout\_dependent* присвоено значение **false**, соглашение о вызове и класс хранения \(виртуальный, статический и так далее\) может смешиваться и в разных сочетаниях использоваться в методах запуска событий и методах прикрепления \(вторые являются делегатами первых\).  Несколько более эффективно, если параметр *layout\_dependent* имеет значение **true**.  
  
 Например, предположим, что `IEventSource` определен как объект, имеющий следующие методы.  
  
```  
[id(1)] HRESULT MyEvent1([in] int value);  
[id(2)] HRESULT MyEvent2([in] int value);  
```  
  
 Предположим, источник событий имеет следующую форму:  
  
```  
[coclass, event_source(com)]  
class CSource : public IEventSource {  
public:  
   __event __interface IEvents;  
  
   HRESULT FireEvent() {  
      MyEvent1(123);  
      MyEvent2(123);  
      return S_OK;  
   }  
};  
```  
  
 Затем в приемнике событий любой обработчик, который прикрепляется к методу в `IEventSource`, должен соответствовать имени и подписи следующим образом.  
  
```  
[coclass, event_receiver(com, true)]  
class CReceiver {  
public:  
   HRESULT MyEvent1(int nValue) {  // name and signature matches MyEvent1  
      ...  
   }  
   HRESULT MyEvent2(E c, char* pc) {  // signature doesn't match MyEvent2  
      ...  
   }  
   HRESULT MyHandler1(int nValue) {  // name doesn't match MyEvent1 (or 2)  
      ...  
   }  
   void HookEvent(IEventSource* pSource) {  
      __hook(IFace, pSource);  // Hooks up all name-matched events   
                               // under layout_dependent = true  
      __hook(&IFace::MyEvent1, pSource, &CReceive::MyEvent1);   // valid  
      __hook(&IFace::MyEvent2, pSource, &CSink::MyEvent2);   // not valid  
      __hook(&IFace::MyEvent1, pSource, &CSink:: MyHandler1); // not valid  
   }  
};  
```  
  
## См. также  
 [Обработка событий](../cpp/event-handling.md)