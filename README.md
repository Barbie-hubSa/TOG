// TOG Transport App UI
import React from "react";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { Input } from "@/components/ui/input";
import { Tabs, TabsList, TabsTrigger, TabsContent } from "@/components/ui/tabs";
import { MapPin, Car, User } from "lucide-react";

export default function TOGApp() {
  return (
    <div className="p-6 max-w-xl mx-auto">
      <h1 className="text-3xl font-bold mb-4">TOG - Transport On the Go</h1>
      <Tabs defaultValue="book">
        <TabsList className="grid grid-cols-3 mb-4">
          <TabsTrigger value="book">Book</TabsTrigger>
          <TabsTrigger value="track">Track</TabsTrigger>
          <TabsTrigger value="driver">Driver</TabsTrigger>
        </TabsList>

        {/* Book Ride Tab */}
        <TabsContent value="book">
          <Card>
            <CardContent className="space-y-4 pt-6">
              <Input placeholder="Pickup Location" icon={<MapPin />} />
              <Input placeholder="Dropoff Location" icon={<MapPin />} />
              <Button className="w-full bg-blue-600 hover:bg-blue-700">Request Ride</Button>
            </CardContent>
          </Card>
        </TabsContent>

        {/* Track Ride Tab */}
        <TabsContent value="track">
          <Card>
            <CardContent className="pt-6">
              <p className="mb-2">Your ride is en route...</p>
              <div className="p-4 bg-gray-100 rounded-xl text-sm">
                Car: Toyota Prius - GT 4231<br />
                Driver: Kwame Boateng<br />
                ETA: 5 mins
              </div>
              <Button className="mt-4 w-full bg-green-600 hover:bg-green-700">Refresh Status</Button>
            </CardContent>
          </Card>
        </TabsContent>

        {/* Driver Details Tab */}
        <TabsContent value="driver">
          <Card>
            <CardContent className="space-y-2 pt-6">
              <div className="flex items-center space-x-4">
                <User className="text-blue-600" />
                <div>
                  <p className="font-semibold">Kwame Boateng</p>
                  <p className="text-sm text-gray-500">Rating: 4.9/5</p>
                </div>
              </div>
              <div className="flex items-center space-x-4">
                <Car className="text-gray-600" />
                <div>
                  <p className="font-semibold">Toyota Prius</p>
                  <p className="text-sm text-gray-500">Plate: GT 4231</p>
                </div>
              </div>
            </CardContent>
          </Card>
        </TabsContent>
      </Tabs>
    </div>
  );
}
