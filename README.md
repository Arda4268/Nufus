#include <iostream>
#include <string>

using namespace std;

// Türkiye'deki toplam şehir sayısı (81)
const int CITY_COUNT = 81;

int main() {
    string cities[CITY_COUNT] = {
            "Adana", "Adıyaman", "Afyonkarahisar", "Agrı", "Amasya", "Ankara", "Antalya", "Artvin", "Aydin", "Balikesir",
            "Bilecik", "Bingöl", "Bitlis", "Bolu", "Burdur", "Bursa", "Canakkale", "Cankiri", "Corum", "Denizli",
            "Diyarbakir", "Edirne", "Elazig", "Erzincan", "Erzurum", "Eskisehir", "Gaziantep", "Giresun", "Gumuşhane", "Hakkari",
            "Hatay", "Isparta", "Mersin", "Istanbul", "Izmir", "Kars", "Kastamonu", "Kayseri", "Kirklareli", "Kirsehir",
            "Kocaeli", "Konya", "Kutahya", "Malatya", "Manisa", "Kahramanmaras", "Mardin", "Muğla", "Mus", "Nevsehir",
            "Nigde", "Ordu", "Rize", "Sakarya", "Samsun", "Siirt", "Sinop", "Sivas", "Tekirdağ", "Tokat",
            "Trabzon", "Tunceli", "Sanliurfa", "Usak", "Van", "Yozgat", "Zonguldak", "Aksaray", "Bayburt", "Karaman",
            "Kirikkale", "Batman", "Sırnak", "Bartin", "Ardahan", "Igdir", "Yalova", "Karabuk", "Kilis", "Osmaniye",
            "Duzce"
    };
    int populations[CITY_COUNT] = {
            2237940, 623811, 729483, 539657, 337508, 5747325, 2426356, 170875, 1100192, 1254255,
            219427, 281768, 349396, 311810, 270796, 3056120, 513341, 192428, 526282, 1042662,
            1752996, 407763, 587960, 234747, 762321, 888828, 2108074, 453912, 141702, 280514,
            1624450, 444914, 1841825, 15519267, 4394693, 284923, 383373, 1441538, 360860, 242938,
            1975996, 2254408, 571463, 806156, 1421203, 1158092, 829195, 1003283, 408727, 301552,
            362071, 771932, 348608, 1020874, 1356077, 331070, 216460, 638956, 1130331, 602662,
            816684, 83929, 2245046, 370509, 1123589, 418650, 589703, 333383, 596053, 416366, 255491,
            286687, 644556, 537762, 203824, 94060, 197419, 262234, 288282, 145826, 527824,};


    for (int i = 0; i < CITY_COUNT - 1; ++i) {
        int maxIdx = i;
        for (int j = i + 1; j < CITY_COUNT; ++j) {
            if (populations[j] > populations[maxIdx]) {
                maxIdx = j;
            }
        }

        int tempPop = populations[i];
        populations[i] = populations[maxIdx];
        populations[maxIdx] = tempPop;


        string tempCity = cities[i];
        cities[i] = cities[maxIdx];
        cities[maxIdx] = tempCity;
    }


    cout << "Nufusu en fazla olan 10 sehir:" << endl;
    for (int i = 0; i < 10; ++i) {
        cout << cities[i] << " - Nufus: " << populations[i] << endl;
    }

    return 0;
}
