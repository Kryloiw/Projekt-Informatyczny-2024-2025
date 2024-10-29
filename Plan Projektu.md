<a name="_vnpxukvjnony"></a>

Planu Projektu
System e-commerce do zamawiania Pizzy



<a name="_l9sqg16xn0qd"></a><a name="_udq9183vx2cl"></a>










-----


Wersja: 0.5 
26\.10.2024
#### <a name="_lyvpj0d4owxe"></a>**I. Cel i zakres projektu**
**Cel projektu:** Przygotowanie dokumentacji i planu teoretycznego systemu do zamawiania pizzy online (strona internetowa/aplikacja mobilna) który umożliwia użytkownikom przeglądanie menu, składanie zamówień, płatności online oraz śledzenie statusu zamówienia. Dokumentacja powinna zawierać opis funkcji, harmonogramu prac oraz zasady zarządzania projektem, aby zminimalizować ryzyko podczas przyszłej realizacji.

**Zakres:** Projekt systemu, przygotowanie architektury oprogramowania oraz makiety. Plan testów funkcjonalnych, dostępności oraz bezpieczeństwa

-----
#### <a name="_gjb8ia3gc6v3"></a>**II. Analiza wymagań**
1. **Identyfikacja wymagań funkcjonalnych i niefunkcjonalnych:**
   1. Wymagania funkcjonalne (np. moduł zamówień, płatności, śledzenie zamówienia).
   1. Wymagania niefunkcjonalne (np. wydajność, bezpieczeństwo, dostępność w używaniu).
1. **Analiza konkurencji:**
   1. Analiza istniejących systemów do zamawiania jedzenia (np. UberEats, Wolt, Pyszne.pl).
1. **Określenie grupy docelowej:**
   1. Profil użytkownika (wiek, preferencje dot. platformy).
   1. Wymagania użytkowników (logowanie jako gość, proste płatności, czytelny i łatwo dostępny interfejs).
-----
#### <a name="_mgv1ysbzic1x"></a>**III. Projektowanie funkcji i struktury systemu**
1. **Określenie modułów systemu:**
   1. **Panel użytkownika:** rejestracja/logowanie, odzyskiwanie hasła, wylogowanie, dodawanie adresów dostaw, przegląd zamówień, historia zamówień, edytowanie danych konta, dodawanie produktów do listy ulubionych.
   1. **Panel zamówień:** menu z pizzami, personalizacja pizzy, koszyk, komentarz do zamówienia, wybór adresu dostawy, finalizacja zamówienia, status zamówienia.
   1. **Panel płatności:** systemy płatności, wybór metody płatności (blik, karta, przelew24, gotówka), faktura.
   1. **Panel dostaw:** śledzenie zamówienia, integracja z systemem GPS.
   1. **Panel administracyjny:** zarządzanie produktami, obsługa zamówień, raporty.
1. **Opis architektury systemu:**
   1. Architektura mikro serwisowa; łatwe skalowanie i elastyczność.
   1. Odseparowany front-end (SPA) i back-endu (API) umożliwiająca bezkonfliktowe rozwijanie aplikacji mobilnej i strony internetowej.
1. **Technologie i narzędzia (hipotetyczne):**
   1. **Frontend:** React/Vue.js dla SPA.
   1. **Backend:** Node.js/Django jako serwer aplikacyjny, API RESTful.
   1. **Baza danych:** relacyjna baza danych (PostgreSQL) oraz NoSQL (MongoDB) dla danych użytkowników.
   1. **Bezpieczeństwo:**
      1. Zastosowanie szyfrowania SSL dla wszystkich transmisji danych. Przestrzeganie wymogów RODO (m.in. w zakresie zarządzania danymi użytkowników i praw do ich zapomnienia).
      2. Zarządzanie tajnymi danymi (Vault): HashiCorp Vault do bezpiecznego przechowywania i dystrybucji tajnych danych, takich jak hasła, klucze API czy dane uwierzytelniające. Vault zapewnia dynamiczne zarządzanie dostępem do danych oraz automatyczną rotację kluczy, co minimalizuje ryzyko wycieku danych i pozwala na precyzyjną kontrolę dostępu w ramach infrastruktury aplikacji.
   1. **Cloud (AWS):** infrastruktura hostowana na AWS, wykorzystująca takie usługi jak:
      1. **Amazon EC2** do skalowalnych instancji serwerowych,
      2. **Amazon S3** do przechowywania plików statycznych i kopii zapasowych,
      3. **Amazon RDS** dla zarządzanych baz danych PostgreSQL oraz MongoDB Atlas jako zarządzanego rozwiązania NoSQL.
   1. **Infrastruktura jako kod (IaC):** Terraform do zarządzania infrastrukturą AWS jako kodem, pozwalający na automatyczne wdrażanie i aktualizowanie zasobów.
   1. **Orkiestracja kontenerów (Nomad)**: HashiCorp Nomad do zarządzania kontenerami aplikacji (Node.js/Django). Nomad, w połączeniu z Consulem (do service discovery) i Vaultem (do zarządzania tajnymi danymi), umożliwia automatyczne wdrażanie i monitorowanie aplikacji na kontenerach, zachowując skalowalność i elastyczność.
   1. **Usługi discovery i sieciowe (Consul):** HashiCorp Consul, który obsługuje service discovery oraz sieciowe połączenia między mikrousługami. Consul automatycznie monitoruje i rejestruje usługi, zapewniając bezpieczną komunikację i dynamiczny load balancing, co pozwala aplikacji na efektywne skalowanie w zależności od obciążenia.
   1. **Monitoring i observability:** System monitorowania (Prometheus + Grafana) do zbierania metryk i logów z infrastruktury oraz aplikacji, umożliwiający szybkie wykrywanie i reagowanie na problemy w działaniu aplikacji.
   1. **System alertowania:** Alertmanager, który pozwala na automatyczne powiadomienia w przypadku przekroczenia progów krytycznych, co przyspiesza reakcję na problemy.
   1. **Zarządzanie logami:** Loki + Grafana, co umożliwia szybkie przeszukiwanie logów i identyfikację problemów.
   1. **Automatyzacja CI/CD:** Jenkins, do automatyzacji wdrożeń i testów, co umożliwia częstsze i bezpieczniejsze wdrożenia.
-----
#### <a name="_q7dozito4mpv"></a>**IV. Projekt makiety**
1. **Makieta i prototyp:**
   1. Tworzenie low-fidelity makiet (szkiców) dla szybkiego feedbacku podczas spotkań i high-fidelity prototypów do prezentacji wizualnej.
1. **Proces projektowania interfejsu:**
   1. Wykorzystanie narzędzi takich jak Figma lub Adobe XD.
   1. Skupienie na dostępności i wydajności.
1. **Interfejs użytkownika:**
   1. Przejrzysty i intuicyjny. Skupiony na wygodzie składania zamówienia i korzystania z menu.
   1. Elementy takie jak szybki dostęp do listy ulubionych produktów, łatwy wybór dodatków do pizzy.
-----
#### <a name="_oir2fo7i376i"></a>**V. Harmonogram prac projektowych**
**Faza 1: Dokumentacja i analizy**

- **Cel:** Sporządzenie kompletnej dokumentacji projektu.
- **Czas trwania:** 3-4 tygodnie
- **Rezultaty:** Dokument wymagań funkcjonalnych i niefunkcjonalnych, raport z badania rynku i konkurencji.

**Faza 2: Architektura systemu i projektowanie technologiczne**

- **Cel:** Stworzenie architektury systemu, wybór narzędzi i technologii.
- **Czas trwania:** 2 tygodnie
- **Rezultaty:** Dokument architektury oprogramowania i specyfikacja technologiczna.

**Faza 3: Projektowanie interfejsu i UX/UI**

- **Cel:** Stworzenie makiet i prototypów.
- **Czas trwania:** 2 tygodnie
- **Rezultaty:** Kompletne makiety oraz projekt UX/UI.

**Faza 4: Planowanie testów i kontroli jakości**

- **Cel:** Stworzenie szczegółowego planu testów.
- **Czas trwania:** 1 tydzień
- **Rezultaty:** Plan testów funkcjonalnych, wydajnościowych, bezpieczeństwa.
  -----
  #### <a name="_9mp51pjzcb37"></a>**VI. Zarządzanie projektem i komunikacja**
1. **Metodologia:** Agile lub Scrum z teoretycznymi iteracjami (sprinty i retrospektywy) umożliwiającymi regularne przeglądy postępu.
1. **Narzędzia do zarządzania:**
   1. **Jira** – dla symulacji zarządzania zadaniami.
   1. **MS Teams** – dla komunikacji projektowej.
1. **Struktura zespołu projektowego:**
   1. Role:  Project Manager (dla zarządzania wymaganiami i Jirą), Analityk biznesowy (analiza wymagań), Architekt (projektowanie architektury), UX/UI Designer (makieta), Tester.
1. **Raportowanie i monitorowanie:**
   1. **Cotygodniowe spotkania statusowe** w celu omówienia założeń i przeglądu teorii.
   1. **Taski i komentarze w Jirze** na etapach projektu.
-----
#### <a name="_w2j6z5t1onem"></a>**VII. Dokumentacja**
1. **x**
   1. x
   1. x
1. **x**
   1. x
   1. x
1. **x**
   1. x
   1. x
-----
#### <a name="_k9fqt447vb3f"></a>**VIII. Ocena ryzyka i plan zapobiegania**
1. **Opóźnienia w dostarczaniu dokumentacji i projektów teoretycznych**
   1. **Zarządzanie:** Regularne spotkania i przeglądy dokumentacji.
1. **Brak pełnego zrozumienia wymagań technicznych**
   1. **Zarządzanie:** Ścisła współpraca z analitykami i właścicielem produktu na etapie planowania.
1. **Niedoszacowanie wymagań UX/UI**
   1. **Zarządzanie:** Umożliwienie dodatkowych iteracji projektowych i testów makiet.
-----
#### <a name="_m31pcq59qusl"></a>**IX. Plan końcowy i symulacja wdrożenia**
1. **Symulacja wdrożenia:** Przygotowanie końcowej dokumentacji oraz harmonogramu wdrożenia.
1. **Przyszłe iteracje:** Sugerowane kroki dla zespołu deweloperskiego, które mogą posłużyć jako wytyczne do pełnego wdrożenia.


