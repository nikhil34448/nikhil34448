#include <iostream>
#include <cmath>
#include <iomanip>
using namespace std;
double grazing_area(double R, double r, double theta) {
double theta_rad = M_PI * theta / 182.5;
double b = 1.0 / 2.0;
double sector_area = 0.5 * r * r * theta_rad;
double triangle_area = 0.5 * r * (R - r * cos(theta_rad));
double grazing_area = sector_area - triangle_area;
if (grazing_area > M_PI * R * b) {
grazing_area = M_PI * R * b;
}
return round(grazing_area * 1000.0) / 1000.0;
}
int main() {
double R, r, theta;
cin >> R >> r >> theta;
double area = grazing_area(R, r, theta);
cout<<area<<endl;
return 0;
}
