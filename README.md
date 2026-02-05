#include <stdio.h>
<br>
#include <stdlib.h>
<br>
#include <time.h>
<br>
#include <unistd.h>
<br>

// CRC-8 function (polynomial 0x07)
<br>
unsigned char crc8(unsigned char *data, int len)
<br>
{
<br>
    unsigned char crc = 0x00;
    <br>
    unsigned char poly = 0x07;
    <br>

    for (int i = 0; i < len; i++)
    {
        crc ^= data[i];

        for (int j = 0; j < 8; j++)
        {
            if (crc & 0x80)
                crc = (crc << 1) ^ poly;
            else
                crc <<= 1;
        }
    }
    return crc;
}

int main()
<br>
{
<br>
    unsigned char sof = 0xFF;
    <br>
    unsigned char payload[8];
    <br>
    unsigned char crc;

    srand(time(NULL));
    <br>

    while (1)
    {
        for (int i = 0; i < 8; i++)
        {
            payload[i] = rand() % 256;
        }

        crc = crc8(payload, 8);

        printf("%02X ", sof);

        for (int i = 0; i < 8; i++)
        {
            printf("%02X ", payload[i]);
        }

        printf("%02X\n", crc);

        sleep(2);
    }

    return 0;
}
