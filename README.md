#include <math.h>
#include <stdio.h>
#include <stdlib.h>

int nombre_bin_entier,chiffre;


/*procedure qui test si un nombre est binaire ou non*/
void binaire(float *p) {
  float nombre_bin_reel;
  int indicateur_bin=1,tmp,indicateur_bin_reel;
  do{
    nombre_bin_entier = *p;
    nombre_bin_reel = *p - nombre_bin_entier;
    
    while ( nombre_bin_reel - tmp != 0 )
    {
    nombre_bin_reel= nombre_bin_reel * 10;
    tmp= nombre_bin_reel;
    }

    while ( tmp != 0 ) {
      chiffre = tmp % 10;
      if (chiffre != 1 && chiffre != 0) {
        indicateur_bin_reel = 0;
        tmp = 0;
        printf("\nce nombre est pas binaire");
        printf("\n-------------------------------------\nsaisissez un nombre "
               "en binaire : ");
        scanf("%f", p);
      } else {
        indicateur_bin_reel = 1;
        tmp /= 10;
      }
    }
    while ( nombre_bin_entier != 0 ) {
      chiffre = nombre_bin_entier % 10;
      if (chiffre != 1 && chiffre != 0) {
        indicateur_bin = 0;
        nombre_bin_entier = 0;
        printf("\nce nombre est pas binaire");
        printf("\n-------------------------------------\nsaisissez un nombre "
               "en binaire : ");
        scanf("%f", p);
      } else {
        indicateur_bin = 1;
        nombre_bin_entier /= 10;
      }
    }
  } while (indicateur_bin == 0 && indicateur_bin_reel == 0);
}
