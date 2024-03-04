
public class maratonOdevi {

    private String[] studentsName;
    private int[] minute;

    public int[] getMinute() {
        return minute;
    }

    public void setMinute(int[] minute) {
        this.minute = minute;
    }

    public String[] getStudentsName() {
        return studentsName;
    }

    public void setStudentsName(String[] studentsName) {
        this.studentsName = studentsName;
    }

    public maratonOdevi(String[] studentsNameArrays, int[] minuteArrays) {
        studentsName = studentsNameArrays;
        minute = minuteArrays;
    }

    public void ilkUcDerece(String[] studentsName, int[] minute) {
        System.out.println("İlk üçteki öğrenciler:");
        for (int i = 0; i < 3; i++) {
            int enDusukDerece = Integer.MAX_VALUE;
            int enDusukDereceIndex = -1;
            for (int j = 0; j < minute.length; j++) {
                if (minute[j] < enDusukDerece) {
                    enDusukDerece = minute[j];
                    enDusukDereceIndex = j;
                }
            }
            System.out.println(studentsName[enDusukDereceIndex] + ": " + enDusukDerece);
            minute[enDusukDereceIndex] = Integer.MAX_VALUE;
        }
    }

    public void tumOgrenciVeDereceleri() {
        System.out.println("İsim" + "  " + "Derece(Dakika)");
       for (int i=0;i< studentsName.length;i++){
           System.out.println(studentsName[i]+": "+minute[i]);
       }
    }

    public void ogrenciSınıflandırma(){
        int sayac1=0;
        int sayac2=0;
        int sayac3=0;

        for (int i=0;i< minute.length;i++){
            if (minute[i]>=200 && minute[i]<300){
                sayac1++;
            } else if (minute[i]>=300 && minute[i]<400) {
            sayac2++;
            } else if (minute[i]>=400) {
                sayac3++;
            }
        }
        System.out.println("Öğrencilerin Sınıflandırılması");
        System.out.println("A ->"+sayac3);
        System.out.println("B ->"+sayac2);
        System.out.println("C ->"+sayac1);
    }



    public static void main(String[] args) {
        String[] studentsNameArrays = {"Kadir", "Gökhan", "Hakan", "Suzan", "Pınar", "Mehmet", "Ali", "Emel", "Fırat",
                "James", "Jale", "Ersin", "Deniz", "Gözde", "Anıl", "Burak"};

        int[] minuteArrays = {341, 273, 278, 329, 445, 402, 388, 270, 243, 334, 412, 393, 299, 343, 317, 265};

        maratonOdevi maraton = new maratonOdevi(studentsNameArrays, minuteArrays);
        maraton.tumOgrenciVeDereceleri();
        System.out.println("-----------------------");
        maraton.ilkUcDerece(studentsNameArrays, minuteArrays);
        System.out.println("-----------------------");
        maraton.ogrenciSınıflandırma();

    }
}
