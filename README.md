#include <stdio.h>
#include <stdlib.h>
#include <time.h>
#include <unistd.h>

// CRC-8 function (polynomial 0x07)
unsigned char crc8(unsigned char *data, int len)
{
    unsigned char crc = 0x00;
    unsigned char poly = 0x07;

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
{
    unsigned char sof = 0xFF;
    unsigned char payload[8];
    unsigned char crc;

    srand(time(NULL));

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
