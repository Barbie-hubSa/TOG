// TOG Transport App UI
import React, { useState } from "react";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { Input } from "@/components/ui/input";
import { Tabs, TabsList, TabsTrigger, TabsContent } from "@/components/ui/tabs";
import { MapPin, Car, User } from "lucide-react";

export default function TOGApp() {
  // State to store user input
  const [pickup, setPickup] = useState("");
  const [dropoff, setDropoff] = useState("");

  // What happens when the user clicks "Request Ride"
  const handleRequestRide = () => {
    if (pickup && dropoff) {
      alert(Ride requested from ${pickup} to ${dropoff});
    } else {
      alert("Please enter both pickup and dropoff locations.");
    }
  };

  return (
    <div className="p-6 max-w-md mx-auto">
      <h1 className="text-2xl font-bold mb-4">TOG - Transport On the Go</h1>
      <Tabs defaultValue="book" className="w-full">
        <TabsList className="mb-4">
          <TabsTrigger value="book">Book Ride</TabsTrigger>
          <TabsTrigger value="track">Track Ride</TabsTrigger>
        </TabsList>

        {/* Book Ride Tab */}
        <TabsContent value="book">
          <Card>
            <CardContent className="space-y-4 pt-6">
              <Input
                placeholder="Pickup Location"
                icon={<MapPin />}
                value={pickup}
                onChange={(e) => setPickup(e.target.value)}
              />
              <Input
                placeholder="Dropoff Location"
                icon={<MapPin />}
                value={dropoff}
                onChange={(e) => setDropoff(e.target.value)}
              />
              <Button
                className="w-full bg-blue-600 hover:bg-blue-700"
                onClick={handleRequestRide}
              >
                Request Ride
              </Button>
            </CardContent>
          </Card>
        </TabsContent>

        {/* Track Ride Tab */}
        <TabsContent value="track">
          <Card>
            <CardContent className="pt-6">
              <p className="text-sm mb-2">Your ride is en route...</p>
              <div className="p-4 bg-gray-100 rounded-xl text-sm">
                <p>Car: Toyota Prius - GT 4231HR</p>
                <p>Driver: Kwame Boateng</p>
              </div>
            </CardContent>
          </Card>
        </TabsContent>
      </Tabs>
    </div>
  );
}
